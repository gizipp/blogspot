---
layout: post
title: "Eco Scroll.js : jQuery Library Menarik!"
shorttitle: "Eco Scrool.js : Menarik"
description: "jQuery library menarik dengan kemungkinan tanpa batas untuk diimplementasikan."
category: io
tags: [js, ui, ux]
---

Eco-Scroll.js
Eco-friendly jQuery scroll plugin with inifinite possibilities

goto https://www.juntamng.com/eco-Scroll for details

<!DOCTYPE html>

    <html>
    <head>
    <title>Image Slider</title>
        <style>
            html, body {
                height: 100%;
                width: 100%;
                margin-top:50px;
            }
            #divContainer {
                margin: 10px auto;
                position: relative;
                width: 800px;
                height: 600px;
                border: 2px #000 solid;
                overflow: hidden;
            }
            .eCell {
                position: absolute;
                border: 1px blue solid;
                -webkit-box-sizing: border-box; /* Safari/Chrome, other WebKit */
                -moz-box-sizing: border-box;    /* Firefox, other Gecko */
                box-sizing: border-box;
            }
            .eCell img
            {
                width: 800px;
                height: 600px;
            }
        </style>
    </head>
    <body>
        <h1><center>Image Slider</center></h1>

        <div id="divContainer">
            <div class="wrapper">
            </div>
        </div>

        <script src="https://code.jquery.com/jquery-1.9.1.js"></script>
        <script src="https://code.jquery.com/ui/1.10.1/jquery-ui.js"></script>
        <script src="../js/jquery.eco-scroll.js"></script>
    <script>
    $(function()
        {
            $("#divContainer").ecoScroll({
                itemWidth: "100%",
                itemHeight: "100%",
                rangeX : [-10,10],
                rangeY : [-10,10],
                axis : "x",
                snap: true,
                onShow:function(oParam)
                {
                    if (oParam.bNew)
                        oParam.$e.append("<img src='..//img//img" + Math.abs( (oParam.x + oParam.y*10)%25 ) + ".jpg' />");
                }
            });
        });
    </script>
    </body>
    </html>