---
title: 'Procedura: determinare se due oggetti sono correlati'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b3f5fc017166ba9cf28359db5de850c81b73bd69
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348621"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="66ae5-102">Procedura: determinare se due oggetti sono correlati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66ae5-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="66ae5-103">È possibile confrontare due oggetti per determinare la relazione, se presente, tra le classi da cui vengono create.</span><span class="sxs-lookup"><span data-stu-id="66ae5-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="66ae5-104">Il metodo <xref:System.Type.IsInstanceOfType%2A> della classe <xref:System.Type?displayProperty=nameWithType> restituisce `True` se la classe specificata eredita dalla classe corrente o se il tipo corrente è un'interfaccia supportata dalla classe specificata.</span><span class="sxs-lookup"><span data-stu-id="66ae5-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="66ae5-105">Per determinare se un oggetto eredita dalla classe o dall'interfaccia di un altro oggetto</span><span class="sxs-lookup"><span data-stu-id="66ae5-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="66ae5-106">Nell'oggetto che si ritiene possa essere del tipo di base, richiamare il metodo <xref:System.Object.GetType%2A>.</span><span class="sxs-lookup"><span data-stu-id="66ae5-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="66ae5-107">Nell'oggetto <xref:System.Type?displayProperty=nameWithType> restituito da <xref:System.Object.GetType%2A>, richiamare il metodo <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="66ae5-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="66ae5-108">Nell'elenco di argomenti per <xref:System.Type.IsInstanceOfType%2A>specificare l'oggetto che si ritiene possa essere del tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="66ae5-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="66ae5-109"><xref:System.Type.IsInstanceOfType%2A> restituisce `True` se il tipo di argomento eredita dal tipo di oggetto <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="66ae5-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="66ae5-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="66ae5-110">Example</span></span>
 <span data-ttu-id="66ae5-111">Nell'esempio seguente viene determinato se un oggetto rappresenta una classe derivata dalla classe di un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="66ae5-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

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

<span data-ttu-id="66ae5-112">Si noti il posizionamento imprevisto delle due variabili oggetto nella chiamata a <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="66ae5-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="66ae5-113">Il tipo di base supposto viene usato per generare la classe <xref:System.Type?displayProperty=nameWithType> e il tipo derivato supposto viene passato come argomento al metodo <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="66ae5-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="66ae5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66ae5-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="66ae5-115">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="66ae5-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="66ae5-116">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="66ae5-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="66ae5-117">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="66ae5-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="66ae5-118">Procedura: determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="66ae5-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
