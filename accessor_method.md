●わからないこと  
 <オブジェクト指向設計入門11>と<オブジェクト指向設計入門12>を読んできた所、アクセサメソッドの自分の認識が合っているのか不安になりました。

●わからないことの詳細
 <オブジェクト指向設計入門11>より  
 ```rb
 class School
  # nameというインスタンスメソッドを定義する
  def name
    @greeting = "Hello!"
  end
  def name1
    # インスタンス変数@greetingは、使用できる
    puts @greeting
  end
end
school = School.new
# @greeting="Hello!"と定義する
school.name
# @greetingの中身を表示する
school.name1
```
というコードに対して、  
>schoolインスタンスに@greeting="Hello!"という属性が保持されていることが確認できます。この保持されたインスタンス変数@greetingの値を外部から読み込むためのメソッドがname1メソッドです。ここでは読み込むための例を出しましたが、このようにインスタンス変数の値を読み書きするメソッドのことをアクセサメソッドと呼びます。

という文面から、
```rb
def name
  @greeting = "Hello!"
end
```
↑こちらのコードが属性の保持に使うコード
```rb
def name1
  # インスタンス変数@greetingは、使用できる
  puts @greeting
end
```
↑こちらのコードがアクセサメソッド  
という認識でした。

そして次の...  
<オブジェクト指向設計入門12>より
```rb
class School
  def name=(word)
    @school_name = word
  end
  def name1
    puts @school_name
  end
end
school = School.new
school.name = "A学校"
school.name1
```
というコードに対して、  
>`school.name = "A学校"`と変数に代入しているように見えますが、name=メソッドが呼び出されています。このようにインスタンス変数の値を読み書きするメソッドのことをアクセサメソッドと呼びます。

という文面から
```rb
def name=(word)
  @school_name = word
end
```
↑こちらのコードが「属性の保持に使うコード」かつ「アクセサメソッド」になった。
(入門11と入門12を比較した場合)

```rb
def name1
  puts @school_name
end
```
↑こちらのコードはアクセサメソッドのまま。  

●アプローチしたこと
教材を再度確認しました。
教材の内容から <オブジェクト指向設計入門11>では...  
nameメソッドは「属性の保持」  
name1メソッドは「アクセサメソッド」  

<オブジェクト指向設計入門12>では、    
nameメソッドは「属性の保持もするアクセサメソッド」  
name1メソッドも「アクセサメソッド」  

このように認識をしたのですが、合っていますでしょうか。
