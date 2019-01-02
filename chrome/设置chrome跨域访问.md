# Chrome：Http请求跨越访问

通过安全设置，可以让chrome浏览器访问非同域下的请求

## Mac下设置

```sh
open -n /Applications/Google\ Chrome.app/ --args --disable-web-security  --user-data-dir=/Users/guofan21/MyChromeDevUserData/
```
设置之后，在a.com下可以访问b.com下的请求，这样前后端联调成本大大降低。