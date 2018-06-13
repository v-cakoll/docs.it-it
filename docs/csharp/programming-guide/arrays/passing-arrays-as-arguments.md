---
title: Passaggio di matrici come argomenti (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: d863cdc33a8a1a844aabbea9ba5876614e6e8dba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315516"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>Passaggio di matrici come argomenti (Guida per programmatori C#)
Le matrici possono essere passate come argomenti ai parametri di metodo. Le matrici, infatti, sono tipi di parametri e il metodo può quindi modificare il valore degli elementi.  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a>Passaggio di matrici unidimensionali come parametri  
 È possibile passare una matrice unidimensionale inizializzata a un metodo. L'istruzione seguente, ad esempio, invia una matrice a un metodo di stampa.  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 Nel codice seguente viene illustrata un'implementazione parziale del metodo di stampa.  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente.  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente, una matrice di stringhe viene inizializzata e passata come argomento a un metodo `PrintArray` per le stringhe. Nel metodo vengono visualizzati gli elementi della matrice. Vengono quindi chiamati i metodi `ChangeArray` e `ChangeArrayElement` per dimostrare che l'invio di un argomento di matrice per valore non impedisce eventuali modifiche agli elementi della matrice.  
  
### <a name="code"></a>Codice  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a>Passaggio di matrici multidimensionali come parametri  
 Una matrice multidimensionale inizializzata viene passata a un metodo nello stesso modo in cui viene passata una matrice unidimensionale.  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 Nel codice seguente viene illustrata una dichiarazione parziale di un metodo di stampa che accetta una matrice bidimensionale come argomento.  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente, una matrice bidimensionale di Integer viene inizializzata e passata al metodo `Print2DArray`. Nel metodo vengono visualizzati gli elementi della matrice.  
  
### <a name="code"></a>Codice  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Array](../../../csharp/programming-guide/arrays/index.md)  
 [Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Matrici irregolari](../../../csharp/programming-guide/arrays/jagged-arrays.md)
