---
title: as - Riferimenti per C#
ms.custom: seodec18
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: b87e75bd4866a191e84465e44d53850e6e2e9723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169923"
---
# <a name="as-c-reference"></a>as (Riferimenti per C#)
È possibile usare l'operatore `as` per eseguire determinati tipi di conversioni tra tipi di riferimenti compatibili o [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md). Il codice seguente illustra un esempio.  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

Come mostrato nell'esempio, è necessario confrontare il risultato dell'espressione `as` con `null` per verificare se la conversione riesce. A partire da C# 7.0, è possibile usare l'espressione [is](is.md) per testare la corretta esecuzione di una conversione e assegnare in modo condizionale una variabile quando la conversione riesce. In molti scenari è più efficace dell'uso dell'operatore `as`. Per altre informazioni, vedere la sezione[Criterio del tipo](is.md#type) dell'articolo [Operatore `is`](is.md).
  
## <a name="remarks"></a>Osservazioni  
 L'operatore `as` è simile a un'operazione cast. Tuttavia, se la conversione non è possibile, `as` restituisce `null` anziché generare un'eccezione. Si consideri l'esempio seguente:  
  
```csharp  
expression as type  
```  
  
 Il codice è equivalente all'espressione seguente, ad eccezione della variabile `expression` che viene restituita una sola volta.  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 Si noti che l'operatore `as` esegue solo conversioni di riferimenti, conversioni nullable e conversioni boxing. L'operatore `as` non può eseguire altre conversioni, ad esempio conversioni definite dall'utente, le quali devono invece essere eseguite tramite le espressioni cast.  
  
## <a name="example"></a>Esempio  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Operatore as](~/_csharplang/spec/expressions.md#the-as-operator) in [Specifica del linguaggio C#](../language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
 
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
- [is](../../../csharp/language-reference/keywords/is.md)
- [?: Operatore](../../../csharp/language-reference/operators/conditional-operator.md)
- [Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md)
