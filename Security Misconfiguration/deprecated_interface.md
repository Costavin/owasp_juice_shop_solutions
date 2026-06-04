# Deprecated Interface  -   &#9733; &#9733;

As we look for the string `B2B` in the main source `main.js`, we notice that in the `Compliant` section was possible to load xml and pdf files. However, it seems we can only load .zip and .pdf files. We can create an empty file, such as `a.xml.zip`, and intercept the loading process through Burp. Once we send the packet to `Repeater`, we can strip the .zip part, and notice that the file is handled somehow.
