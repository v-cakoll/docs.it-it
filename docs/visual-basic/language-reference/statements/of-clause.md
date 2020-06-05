---
title: Clausola Of
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
ms.openlocfilehash: 8497f46453d586fb94e1f7c82c81c6b923dd6f60
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404421"
---
# <a name="of-clause-visual-basic"></a>Clausola Of (Visual Basic)
Introduce una `Of` clausola che identifica un *parametro di tipo* in una classe, una struttura, un'interfaccia, un delegato o una routine *generica* . Per informazioni sui tipi generici, vedere [tipi generici in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Utilizzo della parola chiave of  
 Nell'esempio di codice seguente viene usata la `Of` parola chiave per definire il contorno di una classe che accetta due parametri di tipo. *Vincola* il `keyType` parametro dall' <xref:System.IComparable> interfaccia, il che significa che il codice consumer deve fornire un argomento di tipo che implementi <xref:System.IComparable> . Questa operazione è necessaria in modo che la `add` procedura possa chiamare il <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> metodo. Per altre informazioni sui vincoli, vedere [Type List](type-list.md).  
  
```vb  
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
  
 Se si completa la definizione di classe precedente, è possibile creare una varietà di `dictionary` classi. I tipi forniti `entryType` e `keyType` determinano il tipo di voce che la classe include e il tipo di chiave che associa a ogni voce. A causa del vincolo, è necessario fornire a `keyType` un tipo che implementa <xref:System.IComparable> .  
  
 Nell'esempio di codice seguente viene creato un oggetto contenente le `String` voci e viene associata una `Integer` chiave a ciascuna di esse. `Integer`implementa <xref:System.IComparable> e pertanto soddisfa il vincolo in `keyType` .  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 È possibile usare la parola chiave `Of` nei contesti seguenti:  
  
 [Istruzione Class](class-statement.md)  
  
 [Istruzione Delegate](delegate-statement.md)  
  
 [Istruzione Function](function-statement.md)  
  
 [Istruzione Interface](interface-statement.md)  
  
 [Istruzione Structure](structure-statement.md)  
  
 [Istruzione Sub](sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IComparable>
- [Type List](type-list.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [In](../modifiers/in-generic-modifier.md)
- [Out](../modifiers/out-generic-modifier.md)
