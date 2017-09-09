---
layout:     post
title:      "Alamofire实战记录"
subtitle:   ""
date:       2017-09-3
author:     "Tun"
header-img: "img/Tun-timg.jpeg"
tags:
    - iOS
    - Swift
---

### URLRequestConvertible 协议的使用

创建一个路由枚举，调用效果如下:

~~~
let loginRequest = EnterRouter.login(userPhone, userPassword)
        request(loginRequest).responseJSON { (respone) in
            print(JSON(respone.result.value ?? ""))
        }

~~~

代码如下：
~~~

let baseURL = "http://xxxxx"
var TNParamters = [String: String]()

enum EnterRouter: URLRequestConvertible {
    
    case login(String, String)
    case regist(String, String, String)
    case logout
    
    private var httpMethod: HTTPMethod {
        return .post
    }
    
    private var method: String {
        switch self {
        case .login:
            return "user.login"
        case .regist:
            return "user.regist"
        case .logout:
            return "user.logout"
        }
    }
    
    private var paramters: [String: Any] {
        
        switch self {
        case .login(let userName, let password):
            TNParamters.updateValue(userName, forKey: "phoneNo")
            TNParamters.updateValue(password, forKey: "password")
            return baseParamters
            
        case .regist(let userName, let password, let verifyCode):
            
            TNParamters.updateValue(userName, forKey: "phoneNo")
            TNParamters.updateValue(password, forKey: "password")
            TNParamters.updateValue(verifyCode, forKey: "verifyCode")
            return baseParamters
            
        case .logout:
            
            return baseParamters
        }
    }
    
    private var baseParamters: [String: Any] {
            TNParamters.updateValue(method, forKey: "method")
            return TNParamters
    }
    
    func asURLRequest() throws -> URLRequest {
        
        let url = URL(string: baseURL)
        var request = URLRequest(url: url!)
        request.httpMethod = httpMethod.rawValue
        do {
            let result = try URLEncoding.default.encode(request, with: paramters)
            return result
        } catch let error {
            return request
        }
    }


~~~













