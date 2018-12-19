func minMax(array: [Int]) -> (min: Int, max: Int)? {
   if array.isEmpty { return nil }
   var currentMin = array[0]
   var currentMax = array[0]
   
   for value in array[1..<array.count] {
      if value < currentMin {
         currentMin = value
      } else if value > currentMax {
         currentMax = value
      }
   }
   return (currentMin, currentMax)
}

if let bounds = minMax(array: [8, -6, 2, 109, 3, 71]) {
   print("min is \(bounds.min) and max is \(bounds.max)")
}

==================
[https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html]

func calculateStatistics(scores: [Int]) -> (min: Int, max: Int, sum: Int) {
    var min = scores[0]
    var max = scores[0]
    var sum = 0

    for score in scores {
        if score > max {
            max = score
        } else if score < min {
            min = score
        }
        sum += score
    }

    return (min, max, sum)
}
let statistics = calculateStatistics(scores: [5, 3, 100, 3, 9])
print(statistics.sum)
// Prints "120"
print(statistics.2)
// Prints "120"
