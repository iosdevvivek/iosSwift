override func viewDidLoad() {
    super.viewDidLoad()
    if let titleFont = UIFont(name: "Copperplate", size: 50.0)  {
        let shadow : NSShadow = NSShadow()
        shadow.shadowOffset = CGSizeMake(-2.0, -2.0)
 
        let attributes = [
        NSFontAttributeName : titleFont,
        NSUnderlineStyleAttributeName : 1,
        NSForegroundColorAttributeName : UIColor.whiteColor(),
        NSTextEffectAttributeName : NSTextEffectLetterpressStyle, 
        NSStrokeWidthAttributeName : 3.0,
        NSShadowAttributeName : shadow]
 
        var title = NSAttributedString(string: "NSAttributedString", attributes: attributes) //1
 
        var label = UILabel(frame: CGRectMake(((self.view.bounds.size.width - title.size().width) / 2.0), 40.0, title.size().width, title.size().height)) //2
        label.attributedText = title //3
        view.addSubview(label) //4
    }
}
