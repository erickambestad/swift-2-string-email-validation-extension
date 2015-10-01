A Swift 2 string extension that validates an email address

To use:
```
import Foundation

extension String {
    func isEmail() -> Bool {
        let regex = try! NSRegularExpression(pattern: "^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$",
            options: [.CaseInsensitive])
        
        return regex.firstMatchInString(self, options:[],
            range: NSMakeRange(0, utf16.count)) != nil
    }
}

let email = "test@test.com"

if email.isEmail() {
    print("Valid email address")
} else {
    print("Invalid email address")
}
```
