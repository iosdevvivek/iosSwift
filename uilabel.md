override func viewDidLoad()
{
  super.viewDidLoad()
  var label = UILabel(frame: CGRectMake(0, 0, 200, 21))
  label.center = CGPointMake(160, 284)
  label.textAlignment = NSTextAlignment.Center
  label.text = "I'am a test label"
  self.view.addSubview(label)
}  

3.0:

let label = UILabel(frame: CGRect(x: 0, y: 0, width: 200, height: 21))
label.center = CGPoint(x: 160, y: 285)
label.textAlignment = .center
label.text = "I'am a test label"
self.view.addSubview(label)
