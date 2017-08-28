---
title: Passaggio di matrici mediante ref e out (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 16
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
ms.openlocfilehash: 58fc359881295a9e6627ac1269ef17aa298009c7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a>Passaggio di matrici mediante ref e out (Guida per programmatori C#)
Analogamente a tutti i parametri [out](../../../csharp/language-reference/keywords/out.md), anche il parametro `out` di un tipo di matrice deve essere assegnato prima dell'utilizzo, ovvero assegnato dal chiamato. Ad esempio:  
  
 [!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 Come tutti i parametri [ref](../../../csharp/language-reference/keywords/ref.md), anche il parametro `ref` di un tipo di matrice deve essere assegnato dal chiamante. Non è pertanto necessario che venga assegnato dal chiamato. Il parametro `ref` di un tipo di matrice può risultare modificato in conseguenza della chiamata. È possibile, ad esempio, che alla matrice venga assegnato il valore [null](../../../csharp/language-reference/keywords/null.md) o che venga inizializzata con una matrice diversa. Ad esempio:  
  
 [!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 Nei due esempi che seguono viene illustrata la differenza tra `out` e `ref` quando vengono utilizzati per passare matrici a metodi.  
  
## <a name="example"></a>Esempio  
 In questo esempio la matrice `theArray` viene dichiarata nel chiamante (il metodo `Main`) e inizializzata nel metodo `FillArray`. Gli elementi vengono quindi restituiti al chiamante e visualizzati.  
  
 [!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a>Esempio  
 In questo esempio la matrice `theArray` viene inizializzata nel chiamante (il metodo `Main`) e passata al metodo `FillArray` utilizzando il parametro `ref`. Alcuni degli elementi della matrice vengono aggiornati nel metodo `FillArray`. Gli elementi vengono quindi restituiti al chiamante e visualizzati.  
  
 [!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [Modificatore del parametro out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Matrici](../../../csharp/programming-guide/arrays/index.md)   
 [Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Matrici irregolari](../../../csharp/programming-guide/arrays/jagged-arrays.md)

