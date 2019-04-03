---
title: Conversioni di matrici (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 88002e2c099ed9503beddb190d243aadcc1087fc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830201"
---
# <a name="array-conversions-visual-basic"></a>Conversioni di matrici (Visual Basic)
È possibile convertire un tipo di matrice a un tipo di matrice diversa purché si soddisfino le condizioni seguenti:  
  
-   **Numero di dimensioni uguale.** Le classificazioni delle due matrici devono essere lo stesso, vale a dire deve avere lo stesso numero di dimensioni. Tuttavia, le lunghezze delle rispettive dimensioni non sono necessario essere lo stesso.  
  
-   **Tipo di dati elemento.** I tipi di dati degli elementi di entrambe le matrici devono essere tipi di riferimento. Non è possibile convertire un' `Integer` matrice per un `Long` della matrice, o anche a un `Object` della matrice, in quanto è coinvolta in almeno un tipo valore. Per altre informazioni, vedere [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
-   **Convertibilità della varianza.** Una conversione widening o narrowing, deve essere possibile tra i tipi di elementi delle due matrici. Un esempio che questo requisito non è un tentativo di conversione tra una `String` matrice e una matrice di una classe derivata da <xref:System.Attribute?displayProperty=nameWithType>. Questi due tipi presentano nulla in comune e non esiste alcuna conversione di qualsiasi tipo tra di essi.  
  
 Una conversione del tipo di una matrice a un altro è widening o narrowing a seconda se la conversione degli elementi rispettivi widening o narrowing. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Conversione a una matrice di oggetti  
 Quando si dichiara un `Object` matrice senza inizializzazione, il tipo di elemento è `Object` purché rimane non inizializzata. Se si imposta in una matrice di una classe specifica, assume il tipo di tale classe. Tuttavia, il relativo tipo sottostante è ancora `Object`, ed è possibile impostarlo successivamente in un'altra matrice di una classe non correlata. Poiché tutte le classi di derivano da `Object`, è possibile modificare il tipo di elemento della matrice da una classe a qualsiasi altra classe.  
  
 Nell'esempio seguente, non esiste alcuna conversione tra tipi `student` e `String`, ma entrambi derivano da `Object`, in modo che tutte le assegnazioni sono valide.  
  
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
  
### <a name="underlying-type-of-an-array"></a>Tipo sottostante di una matrice  
 Se inizialmente si dichiara una matrice con una classe specifica, il relativo tipo di elemento sottostante è quella classe. Se è impostarlo successivamente in una matrice di un'altra classe, deve esistere una conversione tra le due classi.  
  
 Nell'esempio riportato di seguito `students` è un `student` matrice. Poiché non esiste alcuna conversione tra `String` e `student`, l'ultima istruzione ha esito negativo.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversioni fra stringhe e altri tipi](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Procedura: Convertire un oggetto in un altro tipo in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
