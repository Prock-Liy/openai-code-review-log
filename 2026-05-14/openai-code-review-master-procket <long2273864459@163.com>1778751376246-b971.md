根据提供的`git diff`记录，以下是对代码变更的评审：

### 1. 引入新的RandomStringUtils类
- **变更**: 在`com.liy.sdk.types.utils`包下新增了`RandomStringUtils`类。
- **原因**: 原因可能是为了提供自定义的随机字符串生成功能，而不是使用Apache Commons Lang库中的`RandomStringUtils`。
- **优点**: 减少了对外部库的依赖，可能提高项目的可维护性和可移植性。
- **缺点**: 如果该功能在项目中很少使用，引入新的类可能会增加项目的复杂性和维护成本。

### 2. 修改RandomStringUtils的导入路径
- **变更**: 将`import org.apache.commons.lang3.RandomStringUtils;`更改为`import com.liy.sdk.types.utils.RandomStringUtils;`。
- **原因**: 可能是代码重构的一部分，将原有的依赖从Apache Commons Lang库转移到自定义的`RandomStringUtils`类。
- **优点**: 如果自定义的类提供了与Apache Commons Lang库中相同的功能，这可以避免潜在的版本冲突和不兼容问题。
- **缺点**: 如果自定义类没有完全实现Apache Commons Lang库中的所有功能，可能会遗漏某些有用的方法。

### 3. 新增RandomStringUtils类的方法
- **变更**: 在`RandomStringUtils`类中新增了`randomNumeric(int length)`方法。
- **优点**: 提供了生成指定长度随机数字字符串的功能，这可能是一个有用的工具方法。
- **缺点**: 如果这个方法的功能已经可以通过其他方式实现，那么添加这个方法可能会造成代码冗余。

### 4. 其他注意事项
- **代码风格**: 应确保代码风格一致，包括命名约定、缩进和注释。
- **单元测试**: 应该为新的`RandomStringUtils`类添加单元测试，以确保其功能的正确性。
- **文档**: 如果新的类和方法是项目的一部分，应该更新相应的文档，以便其他开发者了解其用途和用法。

总的来说，这个变更看起来是为了提高项目的自主性和减少对外部库的依赖。然而，也需要注意可能引入的代码冗余和维护成本。