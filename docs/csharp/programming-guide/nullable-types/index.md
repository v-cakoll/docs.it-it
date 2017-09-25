---
title: Tipi nullable (Guida per programmatori C#)
ms.date: 2017-05-15
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 81117b1419c2a9c3babd6a7429052e2b23e08a70
ms.openlocfilehash: 6d99bffc74cbcce04d725b8f225a4a4b175973be
ms.contentlocale: it-it
ms.lasthandoff: 09/25/2017

---
# <a name="nullable-types-c-programming-guide"></a>Tipi nullable (Guida per programmatori C#)
I tipi nullable sono istanze dello struct <xref:System.Nullable%601?displayProperty=nameWithType>. Un tipo nullable può rappresentare l'intervallo di valori corretto del tipo valore sottostante, più un valore `null` aggiuntivo. Ad esempio, a un tipo `Nullable<Int32>`, detto anche "Nullable of Int32", può essere assegnato qualsiasi valore compreso tra -2147483648 e 2147483647. In alternativa, può essere assegnato il valore `null`. A un tipo `Nullable<bool>` può essere assegnato il valore [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) o [null](../../../csharp/language-reference/keywords/null.md). La possibilità di assegnare il valore `null` a tipi numerici e booleani è particolarmente utile quando si gestiscono database e altri tipi di dati contenenti elementi a cui non è possibile assegnare un valore. Ad esempio, un campo booleano di un database può archiviare i valori `true` o `false` oppure può essere non definito. 
  
[!code-cs[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
Per altri esempi, vedere [Uso dei tipi nullable](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
## <a name="nullable-types-overview"></a>Panoramica dei tipi nullable  
 I tipi nullable hanno le caratteristiche seguenti:  
  
-   I tipi nullable rappresentano variabili di tipo valore a cui può essere assegnato il valore `null`. Non è possibile creare un tipi nullable sulla base di un tipo riferimento. I tipi riferimento supportano già il valore `null`.  
  
-   La sintassi `T?` è l'abbreviazione di <xref:System.Nullable%601>, dove `T` è un tipo valore. Le due forme sono intercambiabili.  
  
-   Per assegnare un valore a un tipo nullable è possibile procedere come per un comune tipo valore, ad esempio `int? x = 10;` o `double? d = 4.108`. A un tipo nullable può essere assegnato anche il valore `null`: `int? x = null.`  
  
-   Usare il metodo <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> per restituire il valore assegnato oppure il valore predefinito del tipo sottostante se il valore è `null`, ad esempio `int j = x.GetValueOrDefault();`  
  
-   Usare le proprietà di sola lettura <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> per verificare la presenza di valori null e recuperare il valore, come illustrato nell'esempio seguente: `if(x.HasValue) j = x.Value;`  
  
    -   La proprietà `HasValue` restituisce `true` se la variabile contiene un valore o `false` se è `null`.  
  
    -   La proprietà `Value` restituisce un valore se ne è stato assegnato uno. In caso contrario viene generata un'eccezione <xref:System.InvalidOperationException?displayProperty=nameWithType>.  
  
    -   Il valore predefinito per la proprietà `HasValue` è `false`. La proprietà `Value` non ha alcun valore predefinito.  
  
    -   Con un tipo nullable è anche possibile usare gli operatori `==` e `!=`, come mostrato nell'esempio seguente: `if (x != null) y = x;`  
  
-   Usare l'operatore `??` per assegnare un valore predefinito che verrà applicato quando un tipo nullable il cui valore corrente è `null` viene assegnato a un tipo non-nullable, ad esempio `int? x = null; int y = x ?? -1;`  
  
-   I tipi nullable nidificati non sono consentiti. La riga seguente non verrà compilata: `Nullable<Nullable<int>> n;`  
  
## <a name="related-sections"></a>Sezioni correlate  
 Per ulteriori informazioni:  
  
-   [Uso dei tipi nullable](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Conversione boxing dei tipi nullable](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [?? (operatore)](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Nullable>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [C#](../../../csharp/index.md)   
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Cosa significa esattamente "elevato"?](http://go.microsoft.com/fwlink/?LinkId=112382)

