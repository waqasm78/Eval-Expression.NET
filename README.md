
###Evaluate, Compile and Execute code and expression in .NET at runtime.###

*From simple expression...*
```csharp
// Eval using Class Member
var price = Eval.Execute("ItemPrice * Quantity", orderItem)


// Eval using Anonymous Type
int result = Eval.Execute<int>("X + Y", new { X = 1, Y = 2})
```
*To complex code.*
```csharp
int result = Eval.Execute<int>(@"
	var list = new List<int>() { 1..100 };
	var filter = list.Where(x => x < 3);
	return result.Sum(x => x);");
```

## Download
<a href="https://www.nuget.org/packages/Z.Expressions.Eval/" target="_blank" alt="download nuget"><img src="https://img.shields.io/nuget/v/Z.Expressions.Eval.svg?style=flat-square" /></a>
<a href="https://www.nuget.org/packages/Z.Expressions.Eval/" target="_blank" alt="download nuget"><img src="https://img.shields.io/nuget/dt/Z.Expressions.Eval.svg?style=flat-square" /></a>

```
PM> Install-Package Z.Expressions.Eval
```
*FREE Version - up to 50 characters

## Eval.Execute
**Evaluate and execute the code or expression.**

_Anonymous Class_

```csharp
int result = Eval.Execute<int>("X + Y", new { X = 1, Y = 2})
```

_Argument Position_

```csharp
int result = Eval.Execute<int>("{0} + {1}", 1, 2)
```

_Class Member_

```csharp
var price = Eval.Execute("ItemPrice * Quantity", orderItem)
```

_Extension Methods_

```csharp
string s = "X + Y";
int result = s.Eval<int>(new { X = 1, Y = 2 });
```
[Learn more](https://github.com/zzzprojects/Eval-Expression.NET/wiki/Eval-Execute)

## Eval.Compile
**Compile a code or an expression and return a delegate of type Func or Action to execute.**

*Using custom Delegate*
```csharp
Func<int> compiled = Eval.Compile<Func<int>>("x + y", new { x = 1, y = 2})
int result = compiled(1);
```

*Using Extension Methods*
```csharp
string code = "x + y";
var compiled = code.Compile<Func<int, int>>("x", "y");
foreach(var item in list)
{
}
```
[Learn more](https://github.com/zzzprojects/Eval-Expression.NET/wiki/Eval-Compile)

## API - Cheat Sheet
Eval | Extension Methods | EvalManager
------------ | ------------ | ------------
Eval.Compile | "string".Compile | Cache
Eval.Compile&lt;TDelegate&gt; | "string".Compile&lt;TDelegate&gt; | DefaultContext
Eval.Execute | "string:.Execute | AddLicense
Eval.Execute&lt;TResult&gt; | "string:.Execute&lt;TResult&gt;

EvalContext | Options | Register
------------ | ------------ | ------------
Compile | CacheKeyPrefix | RegisterAlias
Compile&lt;TDelegate&gt; | UseCache | RegisterAssembly
Execute | UseCaretForExponent | RegisterDomainAssemblies
Execute&lt;TResult&gt; | | RegisterExtensionMethod
Clone | | RegisterGlobalConstant
 | | RegisterGlobalVariable
 | | RegisterStaticMember
 | | RegisterType

## Free VS Pro
Features | FREE Version | [PRO Version](http://eval-expression.net/#pro)
------------ | :-------------: | :-------------:
Maximum Characters | 50 | Unlimited
Commercial License | No | Yes
Royalty-Free | No | Yes
Support & Upgrades (1 year) | No | Yes
Learn more about the [PRO Version](http://eval-expression.net/#pro)

## Support
- [Website](http://eval-expression.net/)
- [Documentation](https://github.com/zzzprojects/Eval-Expression.NET/wiki)
- sales@zzzprojects.com

Contact our outstanding customer support for any request. We usually answer within the next business day, hour, or minutes!

## More Projects
  - [NET Entity Framework Ext.](http://www.zzzprojects.com/products/dotnet-development/entity-framework-extensions/)
  - [NET Bulk Operations](http://www.zzzprojects.com/products/dotnet-development/bulk-operations/)
  - [Eval Expression.NET](http://eval-expression.net/)
  - [Eval SQL.NET](http://eval-sql.net/)


