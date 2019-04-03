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
ms.openlocfilehash: 880570c714292b0c11eef4e2cd4c4b410bb075f1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823441"
---
# <a name="of-clause-visual-basic"></a>Clausola Of (Visual Basic)
Introduce un' `Of` clausola che identifica una *il parametro di tipo* su un *generico* classe, struttura, interfaccia, delegato o procedure. Per informazioni su tipi generici, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Tramite l'utilizzo della parola chiave  
 Il codice seguente viene illustrato come utilizzare il `Of` parola chiave per definire la struttura di una classe che accetta due parametri di tipo. Si *vincola* la `keyType` parametro per il <xref:System.IComparable> interfaccia, che significa che il codice consumer deve fornire un argomento di tipo che implementa <xref:System.IComparable>. Questa operazione è necessaria in modo che il `add` procedure può chiamare il <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> (metodo). Per altre informazioni sui vincoli, vedere [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
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
  
 Dopo aver completato la precedente definizione di classe, è possibile costruire una serie di `dictionary` classi da esso. I tipi forniti da `entryType` e `keyType` determinare il tipo di voce contiene la classe e il tipo di chiave associa ogni voce. A causa del vincolo, è necessario fornire al `keyType` un tipo che implementa <xref:System.IComparable>.  
  
 L'esempio di codice seguente crea un oggetto che contiene `String` voci e associa un `Integer` chiave con ciascuno di essi. `Integer` implementa <xref:System.IComparable> e pertanto soddisfa il vincolo su `keyType`.  
  
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

- <xref:System.IComparable>
- [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
