---
title: as (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 092c30a858df7baeb35bdf28bae53802fb0916d4
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="as-c-reference"></a>as (Riferimenti per C#)
È possibile usare l'operatore `as` per eseguire determinati tipi di conversioni tra tipi di riferimenti compatibili o [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md). Il codice seguente illustra un esempio.  
  
 [!code-csharp[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## <a name="remarks"></a>Note  
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
 [!code-csharp[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [Operatore ?:](../../../csharp/language-reference/operators/conditional-operator.md)  
 [Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md)
