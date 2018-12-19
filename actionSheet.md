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
 
