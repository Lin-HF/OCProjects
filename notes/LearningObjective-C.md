# 162 Objective-C Variables and Constants
## 在 ".h" 文件中创建的变量可以直接在 ".m"文件中引用。

ViewController.h

```
#import <UIKit/UIKit.h>

@interface ViewController : UIViewController {

NSString *word;

int int1;
}

@end
```

声明字符串用 NSString 加 *。

## 声明常量：
字符串：

```
NSString * const word3 = @"David";
```

Integer：

```
const int int2 = 20;
```

# 163. Objective-C Strings
如过要加入label，所有的步骤与写swift相同，不过cmd + drag 到.h文件中。

```
#import <UIKit/UIKit.h>

@interface ViewController : UIViewController {   
NSString *name;
}

@property (weak, nonatomic) IBOutlet UILabel *label;

@end
```

在label中写字符串：

```
name = @"David";
NSString *word = @"Hello";
self.label.text = [NSString stringWithFormat:@"%@ %@, how are you?", word, name];
```
第一个“%@” 对应word， 第二个“%@”对应name。

# 164. Ints - Integers
在label中显示integer运算结果：
ViewController.h：

```
#import <UIKit/UIKit.h>

@interface ViewController : UIViewController {
int score;
int bonus;
int checkpoint;
}

@property (weak, nonatomic) IBOutlet UILabel *label;

@end
```
ViewController.m：

```
score = 100;
bonus = 50;
checkpoint = 100;

int finaleScore = score + bonus + checkpoint;

self.label.text = [NSString stringWithFormat:@"%d", finaleScore];
```
用“%d”来显示integer。

# 165. Floats & Doubles - Decimals 32 & 64 bit

```
float1 = 100.345;
float2 = 343.564;

float calc1 = float1 + float2;

//self.label1.text = [NSString stringWithFormat:@"%f", calc1];
self.label1.text = [NSString stringWithFormat:@"%.2f", calc1];

double1 = 324234.455;
double2 = 45425.3454;

double calc2 = double1 + double2;

self.label2.text = [NSString stringWithFormat:@"%.8f", calc2];
```
用“%f”来显示float和double, “%.1f”保留小数点后一位。

# 166. Boolean
用“BOOL”声明，全是大写。
可以true/false，也可以YES/NO。

```
bool1 = YES;
bool1 = NO;

bool2 = true;
bool2 = false;
```

# 167. Arrays

普通Array：

```
NSArray *array1 = @[@"Apple", @"Banana", @"Lemon", @"Watermelon"];
self.label1.text = array1[3];
```
可变长Array：

```
NSMutableArray *array2 = [[NSMutableArray alloc] initWithObjects:@"Apple", @"Banana", @"Lemon", @"Watermelon", nil];
[array2 addObject:@"Melon"]; // 加到末尾
[array2 insertObject:@"Strawberry" atIndex:0]; //插入
[array2 removeObjectAtIndex:0]; //删除
self.label2.text = array2[0];
```

# 168. If statement

```
BOOL state = false;

if (state == true) {
self.label1.text = @"Allow Access";
} else {
self.label1.text = @"Denny Access";
}


NSString *name = @"Ben";
if ([name isEqualToString:@"David"]) {
self.label2.text = @"Nice name";
} else if ([name isEqualToString:@"Ben"]) {
self.label2.text = @"Nice name";
} else {
self.label2.text = @"Terrible name";
}


int number = 100;

if (number > 50) {
self.label3.text = @"Higher";
} else {
self.label3.text = @"Lower";
}
```
字符串比较“[name isEqualToString:@"David"]”。

# 169. AND OR

```
AND "&&"
OR "||"
```
# 170. For Loops


```
int number;

for (number = 20; number > 0; number -= 1) {
NSLog(@"%i", number);
}
```
"%d"和"%i"的区别：
“%d”是十进制，“%i”是自动探测进制类型。

```
NSLog(@"%i", 12); //12
NSLog(@"%i", 012); //10
NSLog(@"%i", 0x12); //18
```

# 171.While Loop
```
int number = 0;
while (number < 10) {
number += 1;
NSLog(@"%i", number);
}
```

# 172. Switch Statements

```
int number = 1;
switch (number) {
case 1:
NSLog(@"Number 1");
break;
case 2:
NSLog(@"Number 2");
break;
case 3:
NSLog(@"Number 3");
break;
default:
NSLog(@"Not Available");
break;
}
```

# 173.Functions
这个才是重头戏，不过这一节只是个开始。
新建可点击button，会在.h文件中新建Action：

```
- (IBAction)button:(id)sender;
```
然后自动在.m文件中生成function：

```
- (IBAction)button:(id)sender {
self.label1.text = @"Hello";
[self trigger];
}

- (void)trigger {
self.label2.text = @"I got triggered";
}
```
引用function

```
[self trigger];
[self button:nil];
```

