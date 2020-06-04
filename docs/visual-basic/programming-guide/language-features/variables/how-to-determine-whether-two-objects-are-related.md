---
title: 'Procedura: determinare se due oggetti sono correlati'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 30e88a21e737aa57513745899577381ed34151a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410464"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Procedura: determinare se due oggetti sono correlati (Visual Basic)

È possibile confrontare due oggetti per determinare la relazione, se presente, tra le classi da cui vengono create. Il <xref:System.Type.IsInstanceOfType%2A> metodo della <xref:System.Type?displayProperty=nameWithType> classe restituisce `True` se la classe specificata eredita dalla classe corrente o se il tipo corrente è un'interfaccia supportata dalla classe specificata.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Per determinare se un oggetto eredita dalla classe o dall'interfaccia di un altro oggetto

1. Nell'oggetto che si ritiene possa essere del tipo di base, richiamare il <xref:System.Object.GetType%2A> metodo.

2. Per l' <xref:System.Type?displayProperty=nameWithType> oggetto restituito da <xref:System.Object.GetType%2A> , richiamare il <xref:System.Type.IsInstanceOfType%2A> metodo.

3. Nell'elenco di argomenti per <xref:System.Type.IsInstanceOfType%2A> specificare l'oggetto che si ritiene possa essere del tipo derivato.

    <xref:System.Type.IsInstanceOfType%2A>restituisce `True` se il tipo di argomento eredita dal <xref:System.Type?displayProperty=nameWithType> tipo di oggetto.

## <a name="example"></a>Esempio
 Nell'esempio seguente viene determinato se un oggetto rappresenta una classe derivata dalla classe di un altro oggetto.

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

Si noti il posizionamento imprevisto delle due variabili oggetto nella chiamata a <xref:System.Type.IsInstanceOfType%2A> . Il tipo di base supposto viene usato per generare la <xref:System.Type?displayProperty=nameWithType> classe e il tipo derivato supposto viene passato come argomento al <xref:System.Type.IsInstanceOfType%2A> metodo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Variabili oggetto](object-variables.md)
- [Valori di variabili oggetto](object-variable-values.md)
- [Procedura: determinare se due oggetti sono identici](how-to-determine-whether-two-objects-are-identical.md)
