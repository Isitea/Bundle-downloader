Bundle downloader

Downloads a bundle of files using JSZip and fetch api via modifying http request header if needed.

In general, modifying request header doesn't required to download something. But some server refuse a request with checking request header or client blocks a request due to CORS policy.
If one of them is only applied or download a single file, this problem can be resolved by web extension downloads API.
However, if you want to download multiple files as a single bundled file via modifying referer header and ignoring CORS policy, you can't use web extension downloads API for fetching and you can do only one of modifying referer header of ignoring CORS policy.
Therefore, additional permission on webRequest and webRequestBlocking are required to achieve both of them.

Implanting webRequest and webRequestBlocking permission makes extension review duration longer. To avoid this long review duration, this web extension serves downloading support.