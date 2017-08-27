# JSON Formatter and RestKit Model Mapping
Mac Application to create model properties from the JSON for RestKit(https://github.com/RestKit/RestKit)

### Pasting raw JSON

![](https://github.com/mohshin-shah/RestKitModelHelper/blob/master/unformatted.png)

### Formatting JSON

![](https://github.com/mohshin-shah/RestKitModelHelper/blob/master/json.png)

### Getting the properties list
![](https://github.com/mohshin-shah/RestKitModelHelper/blob/master/allprop.png)

### Searching a nested JSON dictionary also works. For example fetching only Users properties
![](https://github.com/mohshin-shah/RestKitModelHelper/blob/master/keypath.png)
![](https://github.com/mohshin-shah/RestKitModelHelper/blob/master/userproperties.png)



#### Use the properties in User.h and mapping data in User.m as below.

In User.h
```
  @property (nonatomic ,strong) NSString *address;
  @property (nonatomic ,strong) NSString *work;
  @property (nonatomic ,strong) NSString *city;
  @property (nonatomic) NSNumber *id;
  @property (nonatomic ,strong) NSString *dob;
  @property (nonatomic) NSNumber *optedin;
  @property (nonatomic ,strong) NSString *email;
  @property (nonatomic ,strong) NSString *name;
```

And in User.m or anywhere else when you need the **mapping**


```
	RKObjectMapping *mapping = [RKObjectMapping mappingForClass:[self class]];
  [mapping addAttributeMappingsFromDictionary:@{
        @"address" : @"address",
        @"work" : @"work",
        @"city" : @"city",
        @"id" : @"id",
        @"dob" : @"dob",
        @"optedin" : @"optedin",
        @"email" : @"email",
        @"name" : @"name"
	 }];
```



There are many known issues there.Please use this for the faster development for json mapping.
