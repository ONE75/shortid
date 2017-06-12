# shortid

[![Build Status](https://travis-ci.org/bolorundurowb/shortid.svg?branch=master)](https://travis-ci.org/bolorundurowb/shortid)  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) [![NuGet Badge](https://buildstats.info/nuget/shortid)](https://www.nuget.org/packages/shortid)

## About ShortId

A csharp library to generate completely random short id's. they can be used as primary keys or unique identifiers. This library is different in that you can specify the length of the id's generated.

## How to use
To make use of the `shortid`, add it to your project via the Nuget package manager UI or console via this command:

```
Install-Package shortid
```

Add the following using command to the top of your csharp code file:

```csharp
using shortid;
```

This gives your code access the classes and methods of the `shortid` namespace.

To generate a unique id of any length between 7 and 14, you call the `Generate` method without parameters.

```csharp
string id = ShortId.Generate();
// id = KXTR_VzGVUoOY
```

If you want to include numbers in the generated id, then you call the `Generate` method with a boolean indicating your preference.

```csharp
string id = ShortId.Generate(true);
// id = O_bBY-YUkJg
```

If you do not want special characters *i.e _ and -* in your generated id, then call the `Generate` method with two boolean parameters, the first indicating whether or not you want numbers and the second indicating whether or not you want special characeters.

```csharp
string id = ShortId.Generate(true, false);
// id = waBfk3z
```

If you want to specify the length of the generated id, call the `Generate` method with an integer parameter which is the desired length.

```csharp
string id = ShortId.Generate(8);
// id = M-snXzBk
```

If you want to control the type of id generated by specifying whether you want numbers, special characters and the length, call the `Generate` method and pass three parameters, the first a boolean stating whether you want numbers, the second a boolean stating whether you want special characters, the last a number indicating your length preference.

```csharp
string id = ShortId.Generate(true, false, 12);
// id = VvoCDPazES_w
```

**NOTE: when specifying the desired length, shorter lengths increase the possibility thata duplicate id would be generated**