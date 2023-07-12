# 構文の比較

同じ役割でも記述の方法が違う点についてメモする

* 扱う言語
    * Python
    * Visual Basic
    * Visual Basic for Application (Excel)
    * C#
    * Java
## 標準出力
* コンソールに文字を出力する
    * 文字列`Hello world`
    * 数値`114514`


### Python
```python
print()
```
```python
print("Hello world")
```
```python
print(114514)
```
### Visual Basic
* 1行目で`System.Console`をインポートする
* 出力後に改行する
    ```VB
    WriteLine()
    ```
* 出力後に改行しない
    ```VB
    Write()
    ```

* 以下改行するときの例
    ```VB
    Imports System.Console
    Module Module1
        Sub main()
            WriteLine("Hello World")
        End Sub
    End Module
    ```
    ```VB
    Imports System.Console
    Module Module1
        Sub main()
            WriteLine(114514)
        End Sub
    End Module
    ```

### Visual Basic for Application (Excel)
イミディエイトウィンドウを有効にする必要があります！

```Visual Basic for Application
Debug.Print()
```

```Visual Basic for Application
Sub main()
    Debug.Print ("Hello world")
End Sub
```
```Visual Basic for Application
Sub main()
    Debug.Print (114514)
End Sub
```
### C#
セミコロン`;`が必要です
```C#
Console.WriteLine()
```
```C#
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Hello World");
    }
}
```
```C#
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Hello World");
    }
}
```
### Java
セミコロン`;`が必要です

```Java
System.out.println()
```

```Java
public class App {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```
```Java
public class App {
    public static void main(String[]) {
        System.out.println(114514);
    }
}
```

## 標準入力
* プログラムにデータを投げ変数に格納
    * 文字列→`s_line`
    * 数値→`i_line`
* `入力してね`と表示させる（省略可）

### Python
```python
s_line = input("文字を入力してね:")
```
```python
i_line = int(input("数値を入力してね:"))
```

### Visual Basic
* データ型に対応した変数の宣言が必要です
```VB
Imports System.Console
Module Module1
    Sub main()
        Dim s_line As String
        Write("文字列を入力してね:") : s_line = ReadLine()
    End Sub
End Module
```
```VB
Imports System.Console
Module Module1
    Sub main()
        Dim s_line As Integer
        Write("数値を入力してね:") : s_line = val(ReadLine())
    End Sub
End Module
```
* 変数の型について
   * [変数の型について - Introduction-To-VBA](https://github.com/matsukz/Introduction-To-VBA#%E5%A4%89%E6%95%B0%E3%81%AE%E5%9E%8B%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6)

### Visual Basic for Application (Excel)
* データ型に対応した変数の宣言が必要です
```Visual Basic for Application
Sub main()
    Dim s_line As String
    s_line = Inputbox("文字列を入力してね")
End Sub
```
```Visual Basic for Application
Sub main()
    Dim s_line As Integer
    i_line = Inputbox("数値を入力してね")
End Sub
```
* 変数の型について
   * [変数の型について - Introduction-To-VBA](https://github.com/matsukz/Introduction-To-VBA#%E5%A4%89%E6%95%B0%E3%81%AE%E5%9E%8B%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6)

### C#
```C#
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("文字列を入力してね");
        String s_line = Console.ReadLine();
    }
}
```
```C#
using System;

class program
{
    static void Main()
    {
        Console.WriteLine("数値を入力してね:");
        int i_line = int.Parse(Console.ReadLine());
    }
}
```
* 宣言済みの変数へ代入するときは、型の宣言は必要ない
    ```C#
    s_line = 代入する値や関数
    ```

### Java
`java.util.Scanner`をインポートする必要があります

```Java
Scanner Scan = new Scanner(System.in);
String s_line = Scan.next();
```
```Java
import java.util.Scanner;
public class App {
    public static void main (String[] args) {
        System.out.println("文字列を入力してね");
        

        Scanner Scan = new Scanner(System.in); //はじめのみ必要
        String s_line = Scan.next();

        System.out.println(s_line)
    }
}
```
* 数値データの場合は`Scan.nextInt();`です
    ```Java
    import java.util.Scanner;
    public class App {
        public static void main (String[] args) {
            System.out.println("数値を入力してね");

            Scanner Scan = new Scanner(System.in); //はじめのみ必要
            int i_line = Scan.nextInt();

            System.out.println(i_line);
        }
    }
    ```
* 宣言済みの変数に代入するときは、型の宣言は必要ない
  ```Java
  s_line = 代入する値
  ``` 
  ```Java
  i_line = Scan.nextInt();
  ```

## 演算
* 四則演算については共通なので省略します

||剰余|べき乗|整数除算|
|------|---|---|---|
|Python|%|**|//|
|VB|Mod|^|\ or Int(x/y)|
|VBA|Mod|^|\|
|C#|%|Math.Pow(x,y)|x/y|
|Java|%|Math.pow(x,y)|x/y|


## 文字列の結合
|言語|演算子|文字列型|数値型|変換|
|---|---|---|---|---|
|Python|+|str|int|必要|
|Visual Basic|&|String|Integer|不要|
|VBA|&|String|Integer|不要|||
|C#|+|String|int|不要|
|Java|+|String|int|不要|

## 条件比較
* 変数`Hensu`の内容によって出力結果を変える
    * `Hensu`が`<0`のとき
      * `(Hensuの値)はマイナスです`と出力
    * `Hensu`が`0`のとき
      * `(Hensuの値)は0です`と出力
    * `Hensu`が`>0`のとき
      * `(Hensuの値)はプラスです`と出力
### Python
```Python
Hensu = int(input())

if Hensu < 0:
    print(str(Hensu) + "はマイナスです")
elif Hensu == 0:
    print(str(Hensu) + "は0です")
else:
    print(str(Hensu) + "はプラスです")
```
### Visual Basic
```VB
Imports System.Console

Module Module1
    Sub main()
        Dim Hensu As Integer

        Write("数値を入力してね") : Hensu = Val(ReadLine())

        If Hensu < 0 Then
            WriteLine(Hensu & "はマイナスです")
        Else If Hensu = 0 Then
            WriteLine(Hensu & "0です")
        Else
            WriteLine(Hensu & "はプラスです")
        End IF
    End Sub
End Module
```

### Visual Basic for Application (Excel)
```VBA
Sub main()
    Dim Hensu As Integer
    
    Hensu = Val(InputBox("数値を入力してね"))

    If Hnesu < 0 Then
        Debug.Print (Hensu & "はマイナスです")
    Else If Hensu = 0 Then
        Debug.Print (Hensu & "は0です")
    Else
        Debug.Print (Hensu & "はプラスです")
    End IF
End Sub
```

### C#
```C#
using System;
class Program
{
    static void Main()
    {
        Console.Write("数値を入力してね:");
        int Hikaku = int.Parse(Console.ReadLine());

        if (Hikaku < 0){
            Console.WriteLine(Hikaku + "はマイナスです");
        } else if (Hikaku == 0) {
            Console.WriteLine(Hikaku + "は0です");
        } else {
            Console.WriteLine(Hikaku + "はプラスです")
        }
    }
}
```

### Java
```Java
import java.util.Scanner;
public class App {
    public static void main (String[] args) {
        System.out.println("数値を入力してね")
        Scanner Scan = new scanner(System.in);
        int Hikaku = Scan.nextInt();

        if (Hikaku < 0) {
            System.out.println(Hikaku + "はマイナスです");
        } else if (Hikaku == 0) {
            System.out.println(Hikaku + "は0です");
        } else {
            System.out.println(Hikaku + "はプラスです");
        }
    }
}
```

## 繰り返し(for)
* 指定した回数分、同じ処理を繰り返す
  * 10回`Hello`を出力
  
### Python
```Python
for i in Rnage(10):
    print("Hello")
```
### Visual Basic
```VB
Imports System.Console
(省略)
For i = 0 To 9
    Console.WriteLine("Hello")
Next i
(省略)
```

### Visual Basic for Application (Excel)
```Visual Basic for Application
(省略)
For i = 0 To 9
    Debug.Print ("Hello")
Next i
(省略)
```

### C#
```C#
using System;
class Main {
    static void main()
    {
        for (int i=0 ;0 < 9 ;i++){
            Console.WriteLine("Hello");
        }
    }

}
```
### Java
```Java
public class App{
    public static void main(String[] args){
        for (int i = 0; i < 9; i++){
            System.out.println("Hello")
        }
    }
}
```
