 private var listDataSource: ListDataSource?

    override func viewDidLoad() {
        super.viewDidLoad()
        listDataSource = ListDataSource(tableView: tableView)
        tableView.dataSource = listDataSource
        tableView.rowHeight = UITableViewAutomaticDimension
        tableView.estimatedRowHeight = 56
        
        ==============
        
        import UIKit;

class ListDataSource: NSObject {

    fileprivate let tableView: UITableView

    init(tableView: UITableView) {
        self.tableView = tableView
        super.init()
        tableView.dataSource = self
        tableView.reloadData()
    }
}

extension ListDataSource: UITableViewDataSource {

    func numberOfSections(in tableView: UITableView) -> Int {
        return 1
    }

    func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return 50
    }

    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = tableView.dequeueReusableCell(withIdentifier: DataCell.reuseIdentifier, for: indexPath)
        configure(cell: cell, indexPath: indexPath)
        return cell
    }

    private func configure(cell: UITableViewCell, indexPath: IndexPath) {
        if let cell = cell as? DataCell {
            cell.configure(object: "Title for row \(indexPath.row)")
        }
    }
}

