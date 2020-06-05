---
title: Conversioni di matrice
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
ms.openlocfilehash: 1d20b01200d3f967e3355dc6e9651291003d140e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402005"
---
# <a name="array-conversions-visual-basic"></a>Conversioni di matrici (Visual Basic)
È possibile convertire un tipo di matrice in un tipo di matrice diverso purché si soddisfino le condizioni seguenti:  
  
- **Rango uguale.** Le classificazioni delle due matrici devono essere uguali, ovvero devono avere lo stesso numero di dimensioni. Tuttavia, non è necessario che le lunghezze delle rispettive dimensioni siano uguali.  
  
- **Tipo di dati dell'elemento.** I tipi di dati degli elementi di entrambe le matrici devono essere tipi di riferimento. Non è possibile convertire una `Integer` matrice in una matrice `Long` o anche in una `Object` matrice perché è necessario almeno un tipo di valore. Per altre informazioni, vedere [Value Types and Reference Types](value-types-and-reference-types.md).  
  
- **Convertibilità della.** È necessario che sia possibile eseguire una conversione verso un tipo di ingrandimento o una riduzione tra i tipi di elemento delle due matrici. Un esempio in cui si verifica un errore di questo requisito è un tentativo di conversione tra una `String` matrice e una matrice di una classe derivata da <xref:System.Attribute?displayProperty=nameWithType> . Questi due tipi non hanno nulla in comune e non esiste alcuna conversione di alcun tipo.  
  
 Una conversione di un tipo di matrice in un altro viene ampliata o ristretta a seconda che la conversione dei rispettivi elementi sia allargata o ridotta. Per altre informazioni, vedere [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Conversione in una matrice di oggetti  
 Quando si dichiara una `Object` matrice senza inizializzarla, il relativo tipo di elemento è purché `Object` rimanga non inizializzato. Quando lo si imposta su una matrice di una classe specifica, viene utilizzato il tipo di tale classe. Tuttavia, il tipo sottostante è ancora `Object` e successivamente è possibile impostarlo su un'altra matrice di una classe non correlata. Poiché tutte le classi derivano da `Object` , è possibile modificare il tipo di elemento della matrice da qualsiasi classe a qualsiasi altra classe.  
  
 Nell'esempio seguente non esiste alcuna conversione tra i tipi `student` e `String` , ma entrambi derivano da `Object` , quindi tutte le assegnazioni sono valide.  
  
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
  
 Nell'esempio seguente `students` è una `student` matrice. Poiché non esiste alcuna conversione tra `String` e `student` , l'ultima istruzione ha esito negativo.  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](index.md)
- [Conversioni di tipi in Visual Basic](type-conversions.md)
- [Conversioni implicite ed esplicite](implicit-and-explicit-conversions.md)
- [Conversioni fra stringhe e altri tipi](conversions-between-strings-and-other-types.md)
- [Procedura: convertire un oggetto in un altro tipo in Visual Basic](how-to-convert-an-object-to-another-type.md)
- [Tipi di dati](../../../language-reference/data-types/index.md)
- [CString](../../../language-reference/functions/type-conversion-functions.md)
- [Matrici](../arrays/index.md)
