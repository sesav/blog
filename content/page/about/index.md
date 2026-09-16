+++
template = "page.html"
slug = "about"
title = "About Sergey"
+++

My name is Sergey Silaev. I am a software engineer, researcher, and backend enthusiast based in Serbia. 

The most efficient and confidential method to reach me is by
<a href="#" id="hide-email" onclick="return false;">email</a> ([pgp](/D2119EAE.asc.txt)).

----

## Social links

[X](https://x.com/sesav_) /
[Bluesky](https://bsky.app/profile/sesav.bsky.social) /
[LinkedIn](https://www.linkedin.com/in/sesav/)

<script>
(function() {
    var hello = "hello";
    var domnain = window.location.hostname;
    var address = hello + "@" + domnain;

    function showEmail(event) {
        var link = document.createElement('a');
        link.href = 'mailto:' + address;
        link.appendChild(document.createTextNode(address));
        event.target.parentNode.replaceChild(link, event.target);
    };

    document.getElementById("hide-email").addEventListener("click", showEmail);
})();
</script>
