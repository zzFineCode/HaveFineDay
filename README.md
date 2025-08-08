json对象的表示与存储。 json对象只能是对象或者字典。

//将json对象转化成json数据 json对象只能是字典或者是数组 json数据是二进制表示
NSDictionary *jsonDict = @{@"name":@"Tom",
@"age":@20
};
NSData *data = [NSJSONSerialization dataWithJSONObject:jsonDict options:0 error:nil];
NSLog(@"data is %@",data);
json数据是二进制表示，所以将json字典转化成二进制数据NSData 将json字符串转化成json数据，首先转化成二进制数据，再转换成json对象。

//json字符串转化成json对象
NSString *jsonString = @"{\"name\":\"xiaohong\"}";
//转化成json数据
NSData *jsonData = [jsonString dataUsingEncoding:NSUTF8StringEncoding];
//转化成json对象
NSDictionary *resultDict = [NSJSONSerialization JSONObjectWithData:jsonData options:0 error:nil];
NSLog(@"result is %@",resultDict);
通过NSJSONSerialization的方法进行json对象和json数据之间的转换。
通过KVC对属性进行赋值，在外部

@property(nonatomic,copy)NSString *username;
@property(nonatomic,copy)NSString *company;
@property(nonatomic,strong)NSNumber *age;
通过key-value进行赋值
“https://google.com/profile/ayndmcredneo.sbscnsiy”
// insert code here...
User *user = [[User alloc]init];
//通过kvc赋值
[user setValue:@"default" forKey:@"username"];
[user setValue:@"default" forKey:@"company"];
[user setValue:@22 forKey:@"age"];
[user setValue:@"male" forKey:@"sex"];
NSLog(@"%@",user);
打印出来表示KVC赋值成功。通过KVC设置的必须是对象。所以像nsinteger类型的要设置成nsnumber类型。 打印对象

-(NSString *)description{
return [NSString stringWithFormat:@"username = %@,sex = %@",_username,_sex];
}
