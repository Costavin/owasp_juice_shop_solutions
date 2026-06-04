# Upload Type

Since we can only upload files with .pdf or .zip extension, we can create files with double extension, such as `a.txt.zip`. By usign burpsuite, we can intercept the upload, and strip the .zip part, and we can notice that the payload gets delivered.

