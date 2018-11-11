shouldStartLoadWith()
extension ViewController: UIWebViewDelegate{
func webView(_ webView: UIWebView, shouldStartLoadWith request:URLRequest, navigationType: UIWebViewNavigationType) -> Bool{
return checkRequestForCallbackURL(request: request)
}
}
func checkRequestForCallbackURL(request: URLRequest) -> Bool {
let requestURLString = (request.url?.absoluteString)! as String
if requestURLString.hasPrefix(API.INSTAGRAM_REDIRECT_URI) {
let range: Range<String.Index> = requestURLString.range(of: “#access_token=”)!
handleAuth(authToken: requestURLString.substring(from: range.upperBound))
return false;
}
return true
