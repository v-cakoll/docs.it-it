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
ms.openlocfilehash: d88c43efe858d6b81b7d8d2470b234ff5d40632a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353836"
---
# <a name="of-clause-visual-basic"></a>Clausola Of (Visual Basic)
Introduce una clausola `Of`, che identifica un *parametro di tipo* in una classe, una struttura, un'interfaccia, un delegato o una routine *generica* . Per informazioni sui tipi generici, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Utilizzo della parola chiave of  
 Nell'esempio di codice seguente viene usata la parola chiave `Of` per definire il contorno di una classe che accetta due parametri di tipo. *Vincola* il parametro `keyType` dall'interfaccia <xref:System.IComparable>, il che significa che il codice consumer deve fornire un argomento di tipo che implementi <xref:System.IComparable>. Questa operazione è necessaria in modo che la procedura `add` possa chiamare il metodo <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType>. Per altre informazioni sui vincoli, vedere [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
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
  
 Se si completa la definizione di classe precedente, è possibile creare una varietà di `dictionary` classi. I tipi forniti per `entryType` e `keyType` determinare il tipo di voce che la classe include e il tipo di chiave che associa a ogni voce. A causa del vincolo, è necessario fornire a `keyType` un tipo che implementi <xref:System.IComparable>.  
  
 Nell'esempio di codice seguente viene creato un oggetto che include `String` voci e associa una chiave di `Integer` a ciascuna di esse. `Integer` implementa <xref:System.IComparable> e pertanto soddisfa il vincolo in `keyType`.  
  
```vb  
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
- [Tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
