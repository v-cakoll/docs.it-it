---
title: 'Procedura: Determinare se due oggetti sono correlati (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2b17be4ef5a7dabfc4779ab6f5675cc2baec9c3c
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626562"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Procedura: Determinare se due oggetti sono correlati (Visual Basic)

È possibile confrontare due oggetti per determinare la relazione, se presente, tra le classi da cui vengono create. Il <xref:System.Type.IsInstanceOfType%2A> metodo `True` della classe restituisce se la classe specificata eredita dalla classe corrente o se il tipo corrente è un'interfaccia supportata dalla classe specificata. <xref:System.Type?displayProperty=nameWithType>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Per determinare se un oggetto eredita dalla classe o dall'interfaccia di un altro oggetto

1. Nell'oggetto che si ritiene possa essere del tipo di base, richiamare il <xref:System.Object.GetType%2A> metodo.

2. Per l' <xref:System.Type?displayProperty=nameWithType> oggetto restituito da <xref:System.Object.GetType%2A>, richiamare il <xref:System.Type.IsInstanceOfType%2A> metodo.

3. Nell'elenco di argomenti per <xref:System.Type.IsInstanceOfType%2A>specificare l'oggetto che si ritiene possa essere del tipo derivato.

    <xref:System.Type.IsInstanceOfType%2A>restituisce `True` se il tipo <xref:System.Type?displayProperty=nameWithType> di argomento eredita dal tipo di oggetto.

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

Si noti il posizionamento imprevisto delle due variabili oggetto nella chiamata a <xref:System.Type.IsInstanceOfType%2A>. Il tipo di base supposto viene usato per <xref:System.Type?displayProperty=nameWithType> generare la classe e il tipo derivato supposto viene passato come argomento <xref:System.Type.IsInstanceOfType%2A> al metodo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Procedura: Determinare se due oggetti sono identici](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
