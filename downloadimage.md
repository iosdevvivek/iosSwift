[https://iosdevcenters.blogspot.com/2018/06/how-to-downloading-image-from-server.html]

extension UIImageView {
    func dowloadFromServer(url: URL, contentMode mode: UIViewContentMode = .scaleAspectFit) {
        contentMode = mode
        URLSession.shared.dataTask(with: url) { data, response, error in
            guard
                let httpURLResponse = response as? HTTPURLResponse, httpURLResponse.statusCode == 200,
                let mimeType = response?.mimeType, mimeType.hasPrefix("image"),
                let data = data, error == nil,
                let image = UIImage(data: data)
                else { return }
            DispatchQueue.main.async() {
                self.image = image
            }
            }.resume()
    }
    func dowloadFromServer(link: String, contentMode mode: UIViewContentMode = .scaleAspectFit) {
        guard let url = URL(string: link) else { return }
        dowloadFromServer(url: url, contentMode: mode)
    }
}

override func viewDidLoad() {
    super.viewDidLoad()
    let imageV = UIImageView(frame: CGRect(x: 90, y: 200, width: 200, height: 200))
    imageV.layer.borderWidth = 5
    imageV.layer.borderColor = UIColor.red.cgColor
    imageV.dowloadFromServer(link: "https://yt3.ggpht.com/a-/ACSszfFprNp-1Ay1IhDjH4NenwvLItZpPHeJdewulw=s900-mo-c-c0xffffffff-rj-k-no", contentMode: .scaleAspectFill)
    self.view.addSubview(imageV)

}
