---
title: Operatori che supportano l'overload (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
ms.openlocfilehash: fcabb7c3f4167d1594d3839eb79034c1667c83dc
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457657"
---
# <a name="overloadable-operators-c-programming-guide"></a>Operatori che supportano l'overload (Guida per programmatori C#)

C# consente ai tipi definiti dall'utente di eseguire l'overload degli operatori definendo le funzioni membro statiche mediante la parola chiave [operator](../../../csharp/language-reference/keywords/operator.md). Non tutti gli operatori, tuttavia, possono essere sottoposti a overload e gli altri sono soggetti alle restrizioni elencate in questa tabella:

| Operatori | Possibilità di overload |
| --------- | --------------- |
|[+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [!](../../../csharp/language-reference/operators/logical-negation-operator.md), [~](../../../csharp/language-reference/operators/bitwise-complement-operator.md), [++](../../../csharp/language-reference/operators/increment-operator.md), [--](../../../csharp/language-reference/operators/decrement-operator.md), [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md)|Questi operatori unari possono essere sottoposti a overload.|
|[+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [\*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md), [%](../../../csharp/language-reference/operators/modulus-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md), [^](../../../csharp/language-reference/operators/xor-operator.md), [\<\<](../../../csharp/language-reference/operators/left-shift-operator.md), [>>](../../../csharp/language-reference/operators/right-shift-operator.md)|Questi operatori binari possono essere sottoposti a overload.|
|[==](../../../csharp/language-reference/operators/equality-comparison-operator.md), [!=](../../../csharp/language-reference/operators/not-equal-operator.md), [\<](../../../csharp/language-reference/operators/less-than-operator.md), [>](../../../csharp/language-reference/operators/greater-than-operator.md), [\<=](../../../csharp/language-reference/operators/less-than-equal-operator.md), [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md)|Gli operatori di confronto possono essere sottoposti a overload (vedere però la nota dopo questa tabella).|
|[&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)|Gli operatori logici condizionali non possono essere sottoposti a overload, ma vengono valutati con `&` e <code>&#124;</code> che possono essere sottoposti a overload.|
|[&#91;&#93;](../../../csharp/language-reference/operators/index-operator.md)|L'operatore di indicizzazione matrice non può essere sottoposto a overload, ma è possibile definire gli indicizzatori.|
|[(T)x](../../../csharp/language-reference/operators/invocation-operator.md)|L'operatore cast non può essere sottoposto a overload, ma è possibile definire nuovi operatori di conversione (vedere [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md)).|
|[+=](../../../csharp/language-reference/operators/addition-assignment-operator.md), [-=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md), [\*=](../../../csharp/language-reference/operators/multiplication-assignment-operator.md), [/=](../../../csharp/language-reference/operators/division-assignment-operator.md), [%=](../../../csharp/language-reference/operators/modulus-assignment-operator.md), [&=](../../../csharp/language-reference/operators/and-assignment-operator.md), [&#124;=](../../../csharp/language-reference/operators/or-assignment-operator.md), [^=](../../../csharp/language-reference/operators/xor-assignment-operator.md), [\<\<=](../../../csharp/language-reference/operators/left-shift-assignment-operator.md), [>>=](../../../csharp/language-reference/operators/right-shift-assignment-operator.md)|Gli operatori di assegnazione non possono essere sottoposti a overload, ma `+=`, ad esempio, viene valutato usando `+`, che possono essere sottoposto a overload.|
|[=](../../../csharp/language-reference/operators/assignment-operator.md), [.](../../../csharp/language-reference/operators/member-access-operator.md), [?:](../../../csharp/language-reference/operators/conditional-operator.md), [??](../../../csharp/language-reference/operators/null-coalescing-operator.md), [->](../../../csharp/language-reference/operators/dereference-operator.md), [=>](../../../csharp/language-reference/operators/lambda-operator.md), [f(x)](../../../csharp/language-reference/operators/invocation-operator.md), [as](../../../csharp/language-reference/keywords/as.md), [checked](../../../csharp/language-reference/keywords/checked.md), [unchecked](../../../csharp/language-reference/keywords/unchecked.md), [default](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../../csharp/language-reference/keywords/is.md), [new](../../../csharp/language-reference/keywords/new.md), [sizeof](../../../csharp/language-reference/keywords/sizeof.md), [typeof](../../../csharp/language-reference/keywords/typeof.md)|Questi operatori non possono essere sottoposti a overload.|

> [!NOTE]
> Gli operatori di confronto, se sottoposti a overload, devono esserlo in coppie, ovvero, se `==` è sottoposto a overload, deve esserlo anche `!=`. È vero anche il contrario e se `!=` è sottoposto a overload deve esserlo anche `==`. Lo stesso vale per gli operatori di confronto `<` e `>` e per `<=` e `>=`.

Per eseguire l'overload di un operatore in una classe personalizzata, è necessario creare un metodo nella classe con la firma corretta. Il metodo deve essere denominato "operator X", dove X è il nome o il simbolo dell'operatore sottoposto a overload. Gli operatori unari hanno un parametro, gli operatori binari invece due parametri. In ogni caso, un parametro deve essere dello stesso tipo della classe o struct che dichiara l'operatore.

```csharp
public static Complex operator +(Complex c1, Complex c2)
{
    return new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);
}
```

È normale che alcune definizioni si limitino a restituire immediatamente il risultato di un'espressione.  Esiste una sintassi breve che in queste situazioni prevede l'uso di `=>`.

```csharp
public static Complex operator +(Complex c1, Complex c2) =>
        new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);
  
// Override ToString() to display a complex number in the traditional format:
public override string ToString() => $"{this.real} + {this.imaginary}";
```

Per altre informazioni, vedere [Procedura: Usare l'overload degli operatori per creare una classe di numeri complessi](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md).

## <a name="see-also"></a>Vedere anche

[Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
[Istruzioni, espressioni e operatori](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
[Operatori](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
[Operatori C#](../../../csharp/language-reference/operators/index.md)  
[Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/) (Perché gli operatori sottoposti a overload sono sempre statici in C#?)
