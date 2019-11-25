---
title: 'How to: Convert an Object to Another Type'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 19708d03b0514f4572c2baa53e05781e5949766b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350065"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Procedura: convertire un oggetto in un altro tipo in Visual Basic
You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Esempio  
 The following example converts an `Object` variable to an `Integer` and a `String`.  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type. If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type). These operations all take extra execution time and make your performance slower.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Object>
- [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversioni fra stringhe e altri tipi](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Conversioni di matrice](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
