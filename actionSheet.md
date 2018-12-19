@IBAction func actionSheetButtonPressed(sender: UIButton) {
 
}

- (IBAction)actionSheetButtonPressed:(id)sender {
    UIAlertController *alert = [UIAlertController alertControllerWithTitle:@"My Alert"
            message:@"This is an action sheet." 
            preferredStyle:UIAlertControllerStyleActionSheet]; // 1
    UIAlertAction *firstAction = [UIAlertAction actionWithTitle:@"one"
            style:UIAlertActionStyleDefault handler:^(UIAlertAction * action) {
                NSLog(@"You pressed button one");
            }]; // 2
    UIAlertAction *secondAction = [UIAlertAction actionWithTitle:@"two"
            style:UIAlertActionStyleDefault handler:^(UIAlertAction * action) {
                NSLog(@"You pressed button two");
            }]; // 3
    
    [alert addAction:firstAction]; // 4
    [alert addAction:secondAction]; // 5
 
    [self presentViewController:alert animated:YES completion:nil]; // 6
}
 
 
 
 
 alert -
 
 @IBAction func alertButtonPressed(sender: UIButton) {
    let alert = UIAlertController(title: "Alert", message: "This is an alert.", preferredStyle: .Alert) // 7
    let defaultAction = UIAlertAction(title: "OK", style: .Default) { (alert: UIAlertAction!) -> Void in
        NSLog("You pressed button OK")
    } // 8
        
    alert.addAction(defaultAction) // 9
    alert.addTextFieldWithConfigurationHandler { (textField: UITextField!) -> Void in
        textField.placeholder = "Input data..."
    } // 10
        
    presentViewController(alert, animated: true, completion:nil)  // 11
}
