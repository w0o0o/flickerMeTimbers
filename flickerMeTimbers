document.querySelector(document).ready(function() {
    var style = document.createElement('style');
    style.type = 'text/css';
    var keyFrames = `@keyframes mainFlicker{0%{opacity:1}9%{opacity:1}10%{opacity:.4}11%{opacity:1}30%{opacity:1}31%{opacity:.4}32%{opacity:1}33%{opacity:.4}34%{opacity:1}100%{opacity:1}}@keyframes flicker{0%{opacity:1}1%{opacity:.4}2%{opacity:1}20%{opacity:1}21%{opacity:.4}22%{opacity:1}23%{opacity:.4}24%{opacity:1}70%{opacity:1}71%{opacity:.4}72%{opacity:1}73%{opacity:.4}74%{opacity:1}}`;
    style.innerHTML = keyFrames.replace(/A_DYNAMIC_VALUE/g, "180deg");
    document.getElementsByTagName('head')[0].appendChild(style);
});

function setFlicker(elementToFlicker, hover = false) {
    document.querySelector(elementToFlicker).each(function() {
        var flickerString = document.querySelector(this).text();
        var flickerArray = flickerString.split("");
        var flickerNewText = "";
        flickerArray.forEach(element => {
            var randomChance = Math.floor(Math.random() * 3);
            if (randomChance == 0) {
                flickerNewText += "<span class='flickerLetter'>" + element + "</span>";
            } else {
                flickerNewText += "<span class='standardLetter'>" + element + "</span>";
            }
        });
        document.querySelector(this).html(flickerNewText);
        if (hover) {
            document.querySelector(this).hover(function() {
                document.querySelector(this).css('animation', 'mainFlicker 4s infinite');
                document.querySelector(this).querySelector('.flickerLetter').each(function() {
                    var randomLength = (Math.random() * 6);
                    document.querySelector(this).css('animation', 'flicker ' + randomLength + 's infinite');
                });
            }, function() {
                document.querySelector(this).css('animation', 'mainFlicker 0s infinite');
                document.querySelector(this).querySelector('.flickerLetter').each(function() {
                    document.querySelector(this).css('animation', 'flicker 0s infinite');
                });
            });
        } else {
            document.querySelector(this).css('animation', 'mainFlicker 4s infinite');
            document.querySelector(this).querySelector('.flickerLetter').each(function() {
                var randomLength = (Math.random() * 6);
                document.querySelector(this).css('animation', 'flicker ' + randomLength + 's infinite');
            });
        }
    });
}
