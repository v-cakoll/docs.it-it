---
title: as (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: 24
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7a55c696ac295eee8d5d35ed56038f3c4a90b215
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="as-c-reference"></a>as (Riferimenti per C#)
È possibile usare l'operatore `as` per eseguire determinati tipi di conversioni tra tipi di riferimenti compatibili o [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md). Il codice seguente illustra un esempio.  
  
 [!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## <a name="remarks"></a>Note  
 L'operatore `as` è simile a un'operazione cast. Tuttavia, se la conversione non è possibile, `as` restituisce `null` anziché generare un'eccezione. Si consideri l'esempio seguente:  
  
```  
expression as type  
```  
  
 Il codice è equivalente all'espressione seguente, ad eccezione della variabile `expression` che viene restituita una sola volta.  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 Si noti che l'operatore `as` esegue solo conversioni di riferimenti, conversioni nullable e conversioni boxing. L'operatore `as` non può eseguire altre conversioni, ad esempio conversioni definite dall'utente, le quali devono invece essere eseguite tramite le espressioni cast.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Operatore ?:](../../../csharp/language-reference/operators/conditional-operator.md)   
 [Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md)

