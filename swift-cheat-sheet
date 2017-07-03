// load from nib
class CustomView: UIView {
  class func loadFromNib(text: String) -> UIView {

    // load UIView from xib
    let podBundle = Bundle(for: self)

    guard let bundleURL = podBundle.url(forResource: "resources", withExtension: "bundle") else {
      fatalError("Cant access bundle url")
    }

    let bundle = Bundle(url: bundleURL)

    guard let view = UINib(nibName: "CustomView", bundle: bundle).instantiate(withOwner: nil, options: nil).first as? HotelDetailMapCell else {
      fatalError("Cant create custom view")
    }

    view.backgroundColor = .green

    return view
  }
}

// UIImage from resource

extension UIImage {
  convenience init?(named: String, for anyClass: AnyClass) {

    let podBundle = Bundle(for: anyClass)

    guard let bundleURL = podBundle.url(forResource: "resources", withExtension: "bundle") else {
      return nil
    }

    let bundle = Bundle(url: bundleURL)

    self.init(named: named, in: bundle, compatibleWith: nil)
  }
}

// get key board height

public extension Notification {

  /**
   Returns the height of the keyboard relative to the given view.
   If the notification doesn't include a keyboard frame, the function returns nil.

   - parameter view: UIView to which the keyboard frame should be calculated.

   - returns: Height of the keyboard frame, if a keyboard is in the Notification.
   */
  func getKeyboardHeight(in view: UIView) -> CGFloat? {

    guard let userInfo = (self as NSNotification).userInfo, let keyboardFrame: AnyObject = userInfo[UIKeyboardFrameEndUserInfoKey] as AnyObject? else {
      return nil
    }

    let rawKeyboardFrame = keyboardFrame.cgRectValue
    let keyboardFrameHeight = view.convert(rawKeyboardFrame!, to: nil).height

    return keyboardFrameHeight
  }
}

// overide init

override init(style: UITableViewCellStyle, reuseIdentifier: String?) {
  super.init(style: style, reuseIdentifier: reuseIdentifier)
  selectionStyle = .none
  setup()
}

required init?(coder aDecoder: NSCoder) {
  super.init(coder: aDecoder)
  setup()
}

// UIView init

required init?(coder aDecoder: NSCoder) {
  super.init(coder: aDecoder)

  setupSubviews()
}

// module pod spec

/*
s.source           = { :git => 'https://.../Module.git', :tag => s.version.to_s }

s.ios.deployment_target = '9.0'

s.resource_bundles = {
  'resources' => [
    'SBWL_Module/Classes/**/*.{storyboard,xib}',
    'SBWL_Module/Classes/**/*.{xcassets}'
  ]
}

s.source_files = 'SBWL_Module/Classes/**/*.{h,m,swift}'

# s.public_header_files = 'Pod/Classes/**/*.h'
# s.frameworks = 'UIKit', 'MapKit'
s.dependency 'Alamofire'
s.dependency 'AlamofireImage'
s.dependency 'ISO8601', '~> 0.6'
*/

// host podfile

/*
def defaultSettings
  use_frameworks!
  platform :ios, '9.0'
  pod 'MyModule', :path => '../MyLocalModule'
end

target 'Customer 1' do
    defaultSettings
end

target 'Customer 2' do
    defaultSettings
end
*/
