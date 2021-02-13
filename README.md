css-circle-animation-1
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="author" content="Zorica Nikolić">
<meta name="description" content="ITAcademy CSS 2nd Assignment">
<title>CSS-assignment-02</title>
<style>
    body {
        margin:0;
        padding:0;
        background-color:#050210;
        height: 100vh;
        width: 100vw;
        display:flex;
        justify-content: center;
        align-items: center;
    }
    
    .circle {
        position: relative;
        margin:0 auto;
        width: 350px;
        height: 350px;
        background: linear-gradient(#fb5dad,#55fb9f,#b97aff);
        border-radius: 100%;
        animation: rotation 0.7s linear infinite;

    }

    /* ********************** FAT BORDER ********************** */
    .circle::after {
        content:'';
        position: absolute;
        top: 25px;
        right: 25px;
        bottom: 25px;
        left: 25px;
        border-radius: 100%;
        background-color: #050210;

    }
    /* ********************** PULSATING INNER CIRCLE ********************** */
    .inner-circle{
        background-color: #0c022e;
        position: absolute;
        width: 300px;
        height: 300px;
        margin: 25px;
        border-radius: 50%;
        z-index: 213;
        animation: pulse 1s linear infinite;
    }
    /* ********************** BORDER GLOW ********************** */
    .circle > span:nth-child(1) {
        position: absolute;
        width: 100%;
        height: 100%;
        background: linear-gradient(#fb5dad,#55fb9f,#b97aff);
        border-radius: 100%;
        filter: blur(50px);
    }
    /* ********************** ANIMATIONS ********************** */
    @keyframes pulse{
        0%{
            transform: scale(0.05);
            opacity: 0.8;
            
        }
        100%{
            transform: scale(1);
            opacity: 0.3;
            
        }
    }
    @keyframes rotation {
        from {
            transform:rotate(0deg);
        }
        to {
            transform: rotate(360deg);
        }
    }
 /* ********************** END STYLE ********************** */
</style>
</head>
<body>
    <div class="circle">
        <span></span>
        <span class="inner-circle"></span>
    </div>
</body>
</html>
