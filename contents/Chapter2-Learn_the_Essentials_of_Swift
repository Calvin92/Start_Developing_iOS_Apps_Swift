# 第二章：学习Swift基础知识

你的第一门课程将会以playground的形式呈现。如第一章所说，playground是一种文件类型，它能让你在其中修改你的Swift代码，并能立即看到代码的运行结果。Playgrounds对于Swift学习和尝试是很棒的一个功能，它能帮助你加速对Swift基础概念的了解。 

###学习目标
在本章的最后，你将掌握以下这些：
  * 区分常量和变量
  * 了解何时使用隐式和显示的类型声明
  * 理解使用可选类型和可选类型绑定的优势
  * 区分可选类型(optionals)和隐式解包的可选类型(implicitly unwrapped optionals)
  * 理解条件语句和循环的目的
  * 超过双重判断条件时使用switch语句来做条件判断
  * 在条件语句中使用where来增加条件约束
  * 区分函数、方法和构造器
  * 区分类，结构体和枚举
  * 理解继承和协议一致性(protocol conformance)的语法
  * 确定隐式的类型，使用Xcode的快速帮助（quick help）快捷方式（Option-Click）查看更多的信息

###基本类型
常量在一开始被声明之后就一直保持同样的值，而变量在声明之后可以被改变。常量意味着它是不可变的，而变量是可变的。如果你一开始就知道你的值在你的代码中就不会改变，那你应该声明它为常量而不是变量。 
使用let创建一个常量，var创建一个变量。 
```
var myVariable = 42
myVariable = 50
let myConstant = 42
```
每个常量和变量在Swift中都有一个类型，但是你不必显式地把类型写出来。当你声明一个常量或者变量的时候，提供给这个常量或者变量一个值，让编译器去推断它的类型。在上面的例子中，编译器推断出myVariable是一个整型，因为它的初始值是一个整型值。这种特性叫做类型推断。一旦常量或者变量有了一个类型，那么这个类型就不能改变。

如果初始值提供不了足够的信息（或者没有初始值），那你需要通过在变量名之后为其指定类型，中间通过冒号分隔。
```
let implicitInteger = 70
let implicitDouble = 70.0
let explicitDouble: Double = 70
```
>动手操作   
>在Xcode中，试试Option-Click(译者注：按住option键再点击，本教程中所有的这种写法的操作都类似)常量或者变量的名字，查看它的推断类型。使用上面代码中的常量去动手尝试。

值永远不会隐式地转换为另一种类型。如果你需要把一个值转换为另一种不同的类型，那你需要显式地创建一个你期望的类型的实例。在下面的例子中，你将转换一个Int类型的值为一个String类型的值。 
```
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```
>动手操作  
>尝试把上面代码最后一行的String去掉。你会发现什么错误？

还有一种更简单的方式把值转换成String类型：在圆括号中写值，并在圆括号中的开始处插入反斜杠“\”。这就是我们熟悉的字符串插值表达式。
```
let apples = 3
let oranges = 5
let appleSummary = "I have \(apples) apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
```
使用可选类型处理值有可能出现值缺失的情况。可选类型的值要么包含一个值，要么就是一个表明值缺失的nil（没有值）。在值的类型后面加上问号（？）以标记该值为可选类型。  
```
let optionalInt: Int? = 9
```
为了从一个可选类型中得到隐含的值，你需要对它进行解包。你稍后将会学习解包可选类型，但是你可以采用最直接的方式－－用强制解包操作符号（！）来进行解包。只有在你确定隐含的值不为nil的时候，你才能用强制解包操作符来进行解包。  
```
let actualInt: Int = optionalInt!
```
可选类型在Swift中是普遍的。在很多情况下，当一个值也许需要又也许不需要呈现的时候，可选类型是非常有用的。  
```
var myString = "7"
var possibleInt = Int(myString)
print(possibleInt)
```
在上面这些代码中，possibleInt的值为7，因为myString包含这个整型的值。但是如果你把myString改成一个不能转换为整型的值的时候，possibleInt将会变成nil。  
```
myString = "banana"
possibleInt = Int(myString)
print(possibleInt)
```
数组是一种能跟踪有序集合中所有项的值的数据类型。使用中括号－－“［］”创建数组，通过在中括号中写入索引来访问数组中的元素。数组是从索引0开始的。  
```
var ratingList = ["Poor", "Fine", "Good", "Excellent"]
ratingList[1] = "OK"
ratingList
```
如果要创建一个空的数组，可以使用初始化语法。稍后，你将会学习到更多关于初始化（译者注：也叫构造器）方面的知识。 
```
// Creates an empty array.
let emptyArray = [String]()
```
你可能注意到上面的代码有一段注释。注释是在源代码文件中的一段文本，其在编译的时候不会被编译器编译，但是它能提供上下文或者关于个人代码片段的有用的信息。单行注释写在双斜杠”//”之后，而多行注释写在一对由斜杠和星号组成的集合之间（/*……*/）。在本教程中，你将会看到并且会写到这两种不同类型的注释。

隐式解包可选类型同样可以作为非可选值，这样就不需要每次访问它们的时候都去对其进行解包。这是因为隐式可选类型在值被初始化之后，我们可以认为它总是有值的，虽然这个值可以变化。隐式解包可选类型使用感叹号（！）来解包，而不是问号（？）。  
```
var implicitlyUnwrappedOptionalInt: Int!
```
在你的代码中，你真的会需要创建隐式解包可选类型。很多时候，你会在在本教程的视图和源代码（你会在接下来的课程中学习关于这方面的东西）之间追踪outlets（译者注：这是一个把视图跟代码连接起来的桥梁）的时候看到它们的存在，在相关的API中，你也会看到它们的存在。  

###控制流
Swift中有两种类型的控制流语句：第一个是条件语句，比如if和switch－－检查一个条件是否是真（true）－－也就是说，在执行一个代码段前，先计算它的值是否是布尔值true，；第二个是循环，比如for-in和while，多次执行相同的代码片段。  

If语句对某一个条件进行检查，如果条件是真（true），就执行在语句体内的代码。你可以通过在if语句中增加else子句定义更复杂的行为。else子句可以和if语句合成为链式使用，也可以自己单独使用－－在这种情况下，如果if的语句的结果不为真（true），那么就会执行else子句。
```
let number = 23
if number < 10 {
    print("The number is small")
} else if number > 100 {
    print("The number is pretty big")
} else {
    print("The number is between 10 and 100")
}
```
在if语句中使用可选绑定来检查可选类型是否有值。  
```
var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
```
>**动手操作**   
>  将optionalName的值修改为nil，greeting会是什么值？增加一个else子句，在optionalName为nil的时候把greeting设置为不同的值。 

如果可选值是nil，那么对应的条件就是false，相对应的括号中的代码就会被忽略。否则，可选值就被解包并赋给let之后的常量，使得被解包出来的值在代码块（if中）中能被使用。

你可以使用单个if语句绑定多个值。where子句可以添加到某一种情形中，以拓展条件语句。在这种情况下，if语句体只有在所有的值都成功绑定和条件都成立之后才被执行。

```
var optionalHello: String? = "Hello"
if let hello = optionalHello where hello.hasPrefix("H"), let name = optionalName {
    greeting = "\(hello), \(name)"
}
```
Swift在Switch中非常强大。一个switch语句支持各种类型的数据和大量的比对操作－－它并不局限于整型和简单地比较相等与否。在下面的例子中，switch语句对vegetable字符串的值在每一种case中进行比对，比对成功则这行相应的代码块。  
```
let vegetable = "red pepper"
switch vegetable {
case "celery":
    let vegetableComment = "Add some raisins and make ants on a log."
case "cucumber", "watercress":
    let vegetableComment = "That would make a good tea sandwich."
case let x where x.hasSuffix("pepper"):
    let vegetableComment = "Is it a spicy \(x)?"
default:
    let vegetableComment = "Everything tastes good in soup."
}
```
>动手操作   
>尝试移除default项，你会发现什么错误？   

注意let是如何在一个匹配的模式中被赋值为常量的。就比如在if语句中，where子句能添加到某一个条件中拓展条件语句。然而，区别于if语句，switch中，有多个通过逗号分隔的条件只要匹配上任何一个，相对应的代码块就会执行。

执行完switch匹配的代码块之后，程序将会从switch语句中退出。程序不会继续执行下一个条件项，所以你不需要在每个条件中显式地退出switch语句体（也就是不需要在每个条件中写break）。

Switch语句必须是详尽的。你需要在每个switch中写上default项，除非你已经明确地从上下文中满足了所有的条件－－比如当switch语句在遍历一个枚举的时候。这个要求确保了总会有一个switch条件被执行。

你可以通过使用范围（range）来获得索引。使用半开的范围操作符来创建一个索引的范围。
```
var firstForLoop = 0
for i in 0..<4 {
    firstForLoop += i
}
print(firstForLoop)
```
半开的范围操作符（..<）不包括最大的数字，所以这个范围是从0到3，总共四次循环迭代。使用封闭的范围操作符（...）创建包括最大和最小数字的范围（range）。  
```
var secondForLoop = 0
for _ in 0...4 {
    secondForLoop += 1
}
print(secondForLoop)
```
这个范围从0到4，总共执行五次循环。下划线（_）表示一个通配符，当你不需要知道循环中当前执行的迭代的时候，你可以使用它去忽略。

###函数和方法
函数是一种可以重复使用，在其中定义了一些代码的代码片段，在整个程序中，函数可以在很多地方被引用。使用func去声明一个函数。函数声明可以包含0个或者多个参数，格式如name:Type。这些参数是额外的信息，当你去调用方法的时候，你必须把这些额外的信息传递进去。另外，函数有可选的返回类型，格式如：->返回类型，这表明这个函数返回的结果。函数的视线写在大括号({})中。
```
func greet(name: String, day: String) -> String {
    return "Hello \(name), today is \(day)."
}
```
通过在函数名字后面加上一个参数（你传进函数中用以满足参数的值）列表来调用函数。当你调用函数的时候，你传进函数中的第一个参数不需要写出它的参数名字，其他的参数值都需要写出对应的名字。  
```
greet("Anna", day: "Tuesday")
greet("Bob", day: "Friday")
greet("Charlie", day: "a nice day")
```
方法(method)是在一个特定的类型中定义的函数。方法（method）会隐式地关联到它所定义的类型上，且只有在这个所关联的类型（或者这个类型的子类，这个概念稍后你会接触到）上才可以调用这个方法。在之前的switch语句的例子中，你看到了定义在String类型上的hasSuffix()方法，这里再看一遍：  
```
let exampleString = "hello"
if exampleString.hasSuffix("lo") {
    print("ends in lo")
}
```
正如你所看到的，调用方法是通过点语法(.)发起调用的。当你调用方法的时候，你传进方法中的第一个参数值不需要写出它对应的名字，而其它每一个参数都带有名字。比如，在数组（Array）中的这个方法需要两个参数，而你只需要为第二个参数加上名字。 
```
var array = ["apple", "banana", "dragonfruit"]
array.insert("cherry", atIndex: 2)
array //译者注：这里的意思应该是打印print(array)
```
###类和构造器
在面向对象编程中，程序的行为主要是基于对象之间的交互的。对象是类（class）的实例，实例可以认为你是对象的蓝图。类使用属性的方式存储关于它们自身的信息，使用方法定义它们的行为。  

通过在class关键字的后面加上类的名字来定义一个类。在类中，属性的写法和定义常量和变量相同，除了它是写在类的上下文中之外。同样地，方法的定义和函数的定义也是类似的。下面的例子声明了一个形状（Shape）类，其定义了一个名字为numberOfSides（边的数量）属性和一个simpleDescription()方法。
```
class Shape {
    var numberOfSides = 0
    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
```
创建一个类的实例，只需要在类的名字后面加上圆括号。使用点操作符（.）去访问实例中的属性和方法。下面的例子中，shape是Shape类的一个实例。  
```
var shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()
```
这个Shape类缺少了一个重要的东西：构造器（initializer）。构造器是在类实例使用之前为实例做准备工作的一个方法，它包括为每一个属性设置一个初始值、执行任何其他的设置。使用init去声明一个构造器。下面的例子定义了一个新的类－－NamedShape，它是一个带有name参数的构造器。  
```
class NamedShape {
    var numberOfSides = 0
    var name: String
    
    init(name: String) {
        self.name = name
    }
    
    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
```
需要注意self是怎么用以区分name属性和构造器中的name参数的。每个属性都需要指定一个值，这个值要么在属性声明中（比如numberOfSides），要么在构造器中（比图name）。   

不要通过直接调用init去执行构造器；你应该通过在类名后面的圆括号中把合适的参数传递进去去调用。当你调用构造器的时候，你需要把所有的参数名字连同它的值传递进去。 
```
let namedShape = NamedShape(name: "my named shape")
```
类可以从它的父类中继承父类的行为。一个类继承了另外一个类的行为，则称这个类为子类（subclass），而被继承的类为父类（或者超类，superclass）。子类在自身的类名后面加上父类的名字，中间通过冒号分隔的形式实现继承。一个类只能继承一个父类，即时父类还可以继承另一个父类，等等，由此形成类层级（class hierarchy）。  

在子类中重写（override）父类的实现是通过override关键字标记的。为了防止意外重写了父类的实现，在没有override标记的时候，重写行为会被编译器当做error（错误）处理。编译器同样会检查在父类中没有存在却被标记为override的方法。 

下面的例子定义了Square类和一个名字为NamedShape的子类。
```
class Square: NamedShape {
    var sideLength: Double
    
    init(sideLength: Double, name: String) {
        self.sideLength = sideLength
        super.init(name: name)
        numberOfSides = 4
    }
    
    func area() ->  Double {
        return sideLength * sideLength
    }
    
    override func simpleDescription() -> String {
        return "A square with sides of length \(sideLength)."
    }
}
let testSquare = Square(sideLength: 5.2, name: "my test square")
testSquare.area()
testSquare.simpleDescription()
```
需要注意Square类的构造器有三个不同的步骤： 
  1. 设置Square子类声明的属性值
  2. 调用父类NamedShape的构造函数
  3. 修改在父类NamedShape中定义的属性值。在这一步，任何额外的通过方法（method），获得方式（get）、设置方式（set）进行的设置工作都可以在这一步进行。

有时候，当提供给参数的值不在预想的范围内，或者当需要的数据缺失的时候，对象的构造函数需要支持构造失败的情况。这种有可能导致对象初始化失败的构造器就做可失败构造器。可失败构造器在初始化的时候有可能会返回nil。使用init?声明一个可失败构造器。 
```
class Circle: NamedShape {
    var radius: Double
    
    init?(radius: Double, name: String) {
        self.radius = radius
        super.init(name: name)
        numberOfSides = 1
        if radius <= 0 {
            return nil
        }
    }
    
    override func simpleDescription() -> String {
        return "A circle with a radius of \(radius)."
    }
}
let successfulCircle = Circle(radius: 4.2, name: "successful circle")
let failedCircle = Circle(radius: -7, name: "failed circle")
```
构造器还可以用一些关键词去修饰。指定构造器（designated initializer）不需要任何的关键词，这种构造器在类中是一种主要的构造器。在类中的任何构造器最终都必须调用一个指定构造器。  

和构造器紧邻的convenience关键词表明这事一个便利构造器。便利构造器是次要的构造器，通过其可以增加额外的行为或定制的服务。但是便利构造器最终必须调用一个指定构造器。  

和构造器紧邻的required关键词表明：在父类中持有必须要在子类实现的构造器时，子类就必须要通过override去实现构造器。  

类型转换是一种检查实例类型的方式，在这个类层次结构中，通过把这个实例当做是一个不同的子类或者父类来检查实例的类型。  

某一个类型的常量或者变量实际上对应一个看不见的子类的实例。当你确信这个类型是具体的类型时，你可以尝试用转换操作将其向下转换（downcast）成子类。  

由于向下转换有可能导致失败，所以类型转换操作会有两种不同的形式。第一种是可选的形式－－as?，这种形式将会返回一个可选的你尝试去转换的类型的值；第二种是强制的形式－－as!，这种形式会做一个复合的操作：尝试去向下转换并且对结果进行强制解包。  

当你不确定向下做类型转换能成功的时候，你可以使用可选类型绑定操作符（optional type cast operator）－－as?。这种形式的操作总会返回一个可选值，如果不能向下转换，这个值将会是nil。这可以让你检查向下类型转换是否成功。  

只有当你确定你的向下转换操作会成功的时候，你才可以使用强制类型转换操作符（forced type cast operator）－－as!。当你尝试转换了一个错误的类型时，这种形式的操作会触发一个运行时错误。  

下面的例子向你展示了可选类型转换操作（as?）的使用：这个例子检查了在shapes数组中的某一项shape是否是一个正方形（square）或者三角形（triangle）。每一次找出Shape时，会对相对应的变量squares和triangles加一，最后输出结果值。  
```
class Triangle: NamedShape {
    init(sideLength: Double, name: String) {
        super.init(name: name)
        numberOfSides = 3
    }
}
 
let shapesArray = [Triangle(sideLength: 1.5, name: "triangle1"), Triangle(sideLength: 4.2, name: "triangle2"), Square(sideLength: 3.2, name: "square1"), Square(sideLength: 2.7, name: "square2")]
var squares = 0
var triangles = 0
for shape in shapesArray {
    if let square = shape as? Square {
        squares++
    } else if let triangle = shape as? Triangle {
        triangles++
    }
}
print("\(squares) squares and \(triangles) triangles.")
```
>**动手操作**  
>尝试将 as?替换成as!。这时候你会捕获到什么错误？  

###枚举和结构体
在Swift中，类不是定义数据类型的唯一的方式。枚举（enumerations）和结构体(structures)和类有相似的功能，但是它们在不同的上下文中却大有用处。 

枚举可以为一组相关的值定义一个公共的类型，它能让你在你的代码中使用一种类型安全的方式去处理这些值。枚举可以拥有与它们相关的方法。  

使用enum创建一个枚举。  
```
enum Rank: Int {
    case Ace = 1
    case Two, Three, Four, Five, Six, Seven, Eight, Nine, Ten
    case Jack, Queen, King
    func simpleDescription() -> String {
        switch self {
        case .Ace:
            return "ace"
        case .Jack:
            return "jack"
        case .Queen:
            return "queen"
        case .King:
            return "king"
        default:
            return String(self.rawValue)
        }
    }
}
let ace = Rank.Ace
let aceRawValue = ace.rawValue
```
在上面的例子中，枚举的原始值的类型是整型（Int），所以你只需要指定第一个原始值。剩余的原始值按照顺序赋值。你同样可以使用字符串或者浮点数作为枚举的原始值。使用rawValue属性可以访问到枚举成员的原始值。  

使用init?(rawValue:)构造函数创建一个从原始值开始的枚举的实例。 
```
if let convertedRank = Rank(rawValue: 3) {
    let threeDescription = convertedRank.simpleDescription()
}
```
枚举的成员值是实际值，而不是通过另外一种方式写的原始值。事实上，在原始值没有实际意义的情况下，你不必提供原始值。 
```
enum Suit {
    case Spades, Hearts, Diamonds, Clubs
    func simpleDescription() -> String {
        switch self {
        case .Spades:
            return "spades"
        case .Hearts:
            return "hearts"
        case .Diamonds:
            return "diamonds"
        case .Clubs:
            return "clubs"
        }
    }
}
let hearts = Suit.Hearts
let heartsDescription = hearts.simpleDescription()
```
注意上面的例子中，枚举中的成员Hearts中两种不同的表示方式：当hearts常量被赋值时，枚举成员Suit.Hearts是它的完整写法，因为常量没有隐式的类型指定。在switch中，枚举成员.Hearts是其简写的形式，因为self的值已经明确地确定为suit。任何时候，在你知道值的类型之后，你可以使用简写的形式。  

结构体和类一样支持很多相同的行为，包括方法和构造器。类和结构体之间最重要的一个区别是：结构体在代码中被传递时总是以复制的形式传递的，但是类是以引用传递的。结构体在定义轻量级的数据类型上是很完美的，它不需要有很多类似于继承和类型转换的功能。   

使用struct来创建一个结构体。  

```
struct Card {
    var rank: Rank
    var suit: Suit
    func simpleDescription() -> String {
        return "The \(rank.simpleDescription()) of \(suit.simpleDescription())"
    }
}
let threeOfSpades = Card(rank: .Three, suit: .Spades)
let threeOfSpadesDescription = threeOfSpades.simpleDescription()
```
###协议
协议是定义了一系列方法、属性和其它特定任务或功能的蓝图。协议事实上不提供任何这些需求的实现，它只是描述了实现的轮廓。协议定义之后可以被一个类、结构体或枚举采用以提供那些需求的具体实现。任何满足了协议的需求的行为，我们称之为遵循（conform）了那个协议。   

使用protocol定义一个协议。  
```
protocol ExampleProtocol {
    var simpleDescription: String { get }
    func adjust()
}
```
>注意  
>在simpleDescription属性之后的{ get }表示这是一个只读的属性，意味着这个属性的值只能获取，不能改变。

协议可以要求遵循它的类型持有指定的实例属性，实例方法，操作符和下标脚本。协议要求遵循它的类型必须实现其中的实例方法和类型方法。这些方法和普通的实例和类型方法一样，定义在协议中，但是没有圆括号或方法体。  

类、结构体和枚举通过在其名字后面写上一个冒号，冒号后列出协议的名字的写法来实现遵循协议。一个类型可以遵循任何数量的协议，协议中间通过逗号分隔。如果类有父类，那么父类必须出现在列表的最前面，后面才跟着协议。你需要通过实现所有的协议的需求来实现协议的遵循。  

下面的例子中，SimpleClass采用了ExampleProtocol协议，通过实现simpleDescription属性和adjust()方法以实现遵循该协议。  
```
class SimpleClass: ExampleProtocol {
    var simpleDescription: String = "A very simple class."
    var anotherProperty: Int = 69105
    func adjust() {
        simpleDescription += "  Now 100% adjusted."
    }
}
var a = SimpleClass()
a.adjust()
let aDescription = a.simpleDescription
```
协议是高级类型，这意味着它们可以当做其它命名过的类型使用。比如，你可以创建一个ExampleProtocol数组，然后在数组的每一个实例中调用adjust()方法（因为在数组中的任何实例会保证实现了adjust()方法－－这是协议的要求）。  
```
class SimpleClass2: ExampleProtocol {
    var simpleDescription: String = "Another very simple class."
    func adjust() {
        simpleDescription += "  Adjusted."
    }
}
 
var protocolArray: [ExampleProtocol] = [SimpleClass(), SimpleClass(), SimpleClass2()]
for instance in protocolArray {
    instance.adjust()
}
protocolArray
```

###Swift和Cocoa Touch框架 
Cocoa Touch是用来开发苹果iOS应用的一个框架的集合，Swift是按照与Cocoa Touch框架无缝衔接来设计的。在你往后的课程的学习中，你会对Swift如何与Cocoa Touch框架进行交互有一个基本的理解。  

至此，你已经学习了Swift标准库中所有的数据类型。Swift标准库(Swift standard library)是为Swift设计的一个数据类型和功能的集合，并将这些融合成为一门语言。在标准库中，像String和Array这样的类型就是数据类型的一些例子。  
```
let sampleString: String = "hello"
let sampleArray: Array = [1, 2, 3.1415, 23, 42]
```
>动手操作   
>通过Option-click在Xcode中的数据类型，查阅Swift标准库中的类型的具体实现。在上面的playground代码中，在String和Array上面Option-click，查看相应的结果。  

当你在开发iOS应用的时候，你不会仅仅使用到Swift标准库。在iOS应用开发中，另一个你会频繁用到的框架是UIKit。UIKit包含了针对应用的UI层级（用户界面，usere interface）设计的有用的类。  

要使用UIKit，只需要在Swift文件或playground文件中简单地把它当做模块导入即可。  
```
import UIKit
```
导入了UIKit之后，你可以使用Swift语法来使用UIKit中的类型以及它们相关的方法、属性等等。  
```
let redSquare = UIView(frame: CGRect(x: 0, y: 0, width: 44, height: 44))
redSquare.backgroundColor = UIColor.redColor()
```
在教程中很多介绍到的类都是来自于UIKit中的，所以你会经常看到这个导入UIKit的语句。  

在经过大量的Swift知识的介绍之后，相信你已经准备好在下一门课程中创建一个功能完整的应用了。虽然这一章节结束之后，你将不会再需要使用到playground了，但是请记住在应用开发中playground是一个很强大的工具，它能帮助你调试，查看上下文代码，提高原型设计效率。