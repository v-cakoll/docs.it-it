---
title: Passaggio di matrici mediante ref e out (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
ms.openlocfilehash: 8da3bf9f8eede72a7bc3cf8380eab66ca2b56e86
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526765"
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a>Passaggio di matrici mediante ref e out (Guida per programmatori C#)

Analogamente a tutti i parametri [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), anche il parametro `out` di un tipo di matrice deve essere assegnato prima dell'utilizzo, ovvero assegnato dal chiamato. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 Come tutti i parametri [ref](../../../csharp/language-reference/keywords/ref.md), anche il parametro `ref` di un tipo di matrice deve essere assegnato dal chiamante. Non è pertanto necessario che venga assegnato dal chiamato. Il parametro `ref` di un tipo di matrice può risultare modificato in conseguenza della chiamata. È possibile, ad esempio, che alla matrice venga assegnato il valore [null](../../../csharp/language-reference/keywords/null.md) o che venga inizializzata con una matrice diversa. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 Nei due esempi che seguono viene illustrata la differenza tra `out` e `ref` quando vengono utilizzati per passare matrici a metodi.  
  
## <a name="example"></a>Esempio

 In questo esempio la matrice `theArray` viene dichiarata nel chiamante (il metodo `Main`) e inizializzata nel metodo `FillArray`. Gli elementi vengono quindi restituiti al chiamante e visualizzati.  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]

## <a name="example"></a>Esempio

 In questo esempio la matrice `theArray` viene inizializzata nel chiamante (il metodo `Main`) e passata al metodo `FillArray` utilizzando il parametro `ref`. Alcuni degli elementi della matrice vengono aggiornati nel metodo `FillArray`. Gli elementi vengono quindi restituiti al chiamante e visualizzati.  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [ref](../../../csharp/language-reference/keywords/ref.md)  
- [Modificatore del parametro out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Array](../../../csharp/programming-guide/arrays/index.md)  
- [Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [Matrici irregolari](../../../csharp/programming-guide/arrays/jagged-arrays.md)
