---
title: Conversioni di matrici (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 40dc9805157dd0bc991ca2375c3436aa6b6e09a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="array-conversions-visual-basic"></a>Conversioni di matrici (Visual Basic)
È possibile convertire un tipo di matrice a un tipo di matrice diversa purché soddisfi le condizioni seguenti:  
  
-   **Numero di dimensioni uguale.** Le classificazioni di due matrici devono essere uguali, vale a dire deve hanno lo stesso numero di dimensioni. Tuttavia, le lunghezze delle rispettive dimensioni non è necessario essere uguali.  
  
-   **Tipo di elemento di dati.** I tipi di dati degli elementi di entrambe le matrici devono essere tipi di riferimento. Non è possibile convertire un `Integer` matrice un `Long` matrice, o anche a un `Object` matrice, in quanto è interessato almeno un tipo valore. Per ulteriori informazioni, vedere [tipi di valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
-   **Possibilità di conversione.** Una conversione widening o narrowing, deve essere possibile tra i tipi di elementi di due matrici. Un esempio di questo requisito non è un tentativo di conversione tra un `String` matrice e una matrice di una classe derivata da <xref:System.Attribute?displayProperty=nameWithType>. Questi due tipi hanno in comune nulla e non esiste alcuna conversione di qualsiasi tipo tra di essi.  
  
 Una conversione di un tipo di matrice a un altro è widening o narrowing a seconda se la conversione dei rispettivi elementi è grande o più piccolo. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Conversione in una matrice di oggetti  
 Quando si dichiara un `Object` matrice senza inizializzarla, il tipo di elemento è `Object` purché rimane non inizializzato. Quando si imposta in una matrice di una classe specifica, assume il tipo di tale classe. Tuttavia, il relativo tipo sottostante è ancora `Object`, ed è possibile impostare successivamente a un'altra matrice di una classe non correlata. Poiché tutte le classi derivano da `Object`, è possibile modificare il tipo di elemento della matrice da una classe in qualsiasi altra classe.  
  
 Nell'esempio seguente, non esiste alcuna conversione tra tipi `student` e `String`, ma entrambi derivano da `Object`, pertanto tutte le assegnazioni sono valide.  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a>Il tipo sottostante di una matrice  
 Se originariamente si dichiara una matrice con una classe specifica, il tipo di elemento sottostante è quella classe. Se si imposta in seguito a una matrice di un'altra classe, deve esistere una conversione tra le due classi.  
  
 Nell'esempio seguente, `students` è un `student` matrice. Poiché non esiste alcuna conversione tra `String` e `student`, l'ultima istruzione ha esito negativo.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Conversioni fra stringhe e altri tipi](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Procedura: convertire un oggetto in un altro tipo in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Array](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
