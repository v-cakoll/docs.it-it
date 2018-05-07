---
title: Clausola Of (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: 9ace0ad55d9eb1618dbdafb0d49d1ff4b169a877
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="of-clause-visual-basic"></a>Clausola Of (Visual Basic)
Introduce un `Of` clausola che identifica un *parametro di tipo* su un *generico* classe, struttura, interfaccia, delegato o stored procedure. Per informazioni sui tipi generici, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Utilizzando la parola chiave  
 Nell'esempio di codice viene illustrato come utilizzare il `Of` (parola chiave) per definire la struttura di una classe che accetta due parametri di tipo. Si *vincola* il `keyType` mediante il <xref:System.IComparable> interfaccia, pertanto il codice consumer deve fornire un argomento di tipo che implementa <xref:System.IComparable>. Questa operazione è necessaria in modo che il `add` procedure può chiamare il <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> metodo. Per ulteriori informazioni sui vincoli, vedere [elenco tipo](../../../visual-basic/language-reference/statements/type-list.md).  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 Se si completa la precedente definizione di classe, è possibile costruire un'ampia gamma di `dictionary` classi da esso. I tipi che si forniscono alla `entryType` e `keyType` determinare il tipo di voce la classe contiene e il tipo di chiave associa ogni voce. A causa del vincolo, è necessario fornire al `keyType` un tipo che implementa <xref:System.IComparable>.  
  
 Esempio di codice seguente crea un oggetto che contiene `String` voci e lo associa un `Integer` chiave con ciascuno di essi. `Integer` implementa <xref:System.IComparable> e pertanto soddisfa il vincolo in `keyType`.  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 È possibile usare la parola chiave `Of` nei contesti seguenti:  
  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IComparable>  
 [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)  
 [Tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
