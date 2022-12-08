```js
var jqry = document.createElement('script');
jqry.src = "https://code.jquery.com/jquery-3.3.1.min.js";
document.getElementsByTagName('head')[0].appendChild(jqry);

var i = 3;

var stepZeroTimer = setInterval(stepZeroFunction,8000);             //RUNS MAIN FUNCTION EVERY 8 SECONDS

function stepZeroFunction()
    {
        var stepOneTimer = setInterval(stepOneFunction,2000);       //CLICKS 3-BUTTON MENU 
        var stepTwoTimer = setInterval(stepTwoFunction,4000);       //CLICKS DELETE
        var stepThreeTimer = setInterval(stepThreeFunction,6000);   //CLICKS OKAY

        function stepOneFunction()
        {
            jQuery(".dropdown-trigger").eq(i).click();
            clearInterval(stepOneTimer);
        }

        function stepTwoFunction()
        {
            if (jQuery(".ytmusic-menu-popup-renderer").eq(4).text().includes("Delete"))
            {
                jQuery(".ytmusic-menu-popup-renderer").eq(4).children().children().eq(0).click();
            }
            if (jQuery(".ytmusic-menu-popup-renderer").eq(5).text().includes("Delete"))
            {
                jQuery(".ytmusic-menu-popup-renderer").eq(5).children().children().eq(0).click();
            }
            if (jQuery(".ytmusic-menu-popup-renderer").eq(6).text().includes("Delete"))
            {
                jQuery(".ytmusic-menu-popup-renderer").eq(6).children().children().eq(0).click();
            }
            clearInterval(stepTwoTimer);
        }

        function stepThreeFunction()
        {
            jQuery("#main").children().eq(3).children().eq(1).click();
            clearInterval(stepThreeTimer);
        }
    }
```