# Upload Size

By using burpsuite, we can intercept a file upload. The chosen file must be smalled than 100KB, and we can see that such an upload is successful. However, once uploaded, we can modify its content (for e.g. by padding it with random bytes) so as to surpass the 100KB limit, and we can notice that the files gets uploaded successfully.
