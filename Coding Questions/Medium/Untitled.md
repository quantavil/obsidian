```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        # Check for the base cases when the nums list is empty or has only one element
        if len(nums) < 2:
            # If nums is empty, return 0. If nums has only one element, return that element
            return nums[0] if nums else 0
        
        # Initialize two variables, prev and curr, to store the maximum amounts of money that
        # can be robbed from houses up to two positions ago and the current position, respectively
        prev, curr = nums[0], max(nums[0], nums[1])
        
        # Iterate through the remaining houses and calculate the maximum amount of money
        # that can be robbed from houses up to the current position
        for i in range(2, len(nums)):
            # Calculate the maximum amount of money that can be robbed from houses up to the
            # current position by choosing the maximum of two options:
            #   1. Robbing the current house and adding its value to the maximum amount that
            #      could be robbed from houses up to two positions ago (prev).
            #   2. Skipping the current house and keeping the maximum amount that could be
            #      robbed from houses up to the previous position (curr).
            new_max = max(prev + nums[i], curr)
            # Update prev and curr for the next iteration of the loop
            prev, curr = curr, new_max
        
        # Return the maximum amount of money that can be robbed from houses up to the last position
        return curr

```