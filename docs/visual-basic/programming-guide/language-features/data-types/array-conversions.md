---
title: Conversioni di matrici
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
ms.openlocfilehash: 622ebe8a77f2dfbeb35e0408be48622d93d409c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345852"
---
# <a name="array-conversions-visual-basic"></a>Conversioni di matrici (Visual Basic)
È possibile convertire un tipo di matrice in un tipo di matrice diverso purché si soddisfino le condizioni seguenti:  
  
- **Rango uguale.** Le classificazioni delle due matrici devono essere uguali, ovvero devono avere lo stesso numero di dimensioni. Tuttavia, non è necessario che le lunghezze delle rispettive dimensioni siano uguali.  
  
- **Tipo di dati dell'elemento.** I tipi di dati degli elementi di entrambe le matrici devono essere tipi di riferimento. Non è possibile convertire una matrice di `Integer` in una matrice di `Long` o anche in una matrice `Object`, perché è necessario almeno un tipo di valore. Per altre informazioni, vedere [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
- **Convertibilità della.** È necessario che sia possibile eseguire una conversione verso un tipo di ingrandimento o una riduzione tra i tipi di elemento delle due matrici. Un esempio in cui si verifica un errore di questo requisito è un tentativo di conversione tra una matrice di `String` e una matrice di una classe derivata da <xref:System.Attribute?displayProperty=nameWithType>. Questi due tipi non hanno nulla in comune e non esiste alcuna conversione di alcun tipo.  
  
 Una conversione di un tipo di matrice in un altro viene ampliata o ristretta a seconda che la conversione dei rispettivi elementi sia allargata o ridotta. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Conversione in una matrice di oggetti  
 Quando si dichiara una matrice di `Object` senza inizializzarla, il relativo tipo di elemento viene `Object` purché rimanga non inizializzato. Quando lo si imposta su una matrice di una classe specifica, viene utilizzato il tipo di tale classe. Tuttavia, il tipo sottostante è ancora `Object`ed è possibile impostarlo successivamente su un'altra matrice di una classe non correlata. Poiché tutte le classi derivano da `Object`, è possibile modificare il tipo di elemento della matrice da qualsiasi classe a qualsiasi altra classe.  
  
 Nell'esempio seguente non esiste alcuna conversione tra i tipi `student` e `String`, ma entrambi derivano da `Object`, quindi tutte le assegnazioni sono valide.  
  
```vb  
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
 Se si dichiara originariamente una matrice con una classe specifica, il relativo tipo di elemento sottostante è tale classe. Se successivamente lo si imposta su una matrice di un'altra classe, è necessario eseguire una conversione tra le due classi.  
  
 Nell'esempio seguente `students` è una matrice di `student`. Poiché non esiste alcuna conversione tra `String` e `student`, l'ultima istruzione ha esito negativo.  
  
```vb  
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
- [Procedura: convertire un oggetto in un altro tipo in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
