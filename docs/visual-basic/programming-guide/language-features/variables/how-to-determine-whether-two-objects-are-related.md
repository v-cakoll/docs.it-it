---
title: 'Procedura: determinare se due oggetti sono correlati (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2041f89ffd954e479046eb85c6dd82de1f8793ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649825"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="9853b-102">Procedura: determinare se due oggetti sono correlati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9853b-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>
<span data-ttu-id="9853b-103">È possibile confrontare due oggetti per determinare la relazione, se presente, tra le classi da cui vengono creati.</span><span class="sxs-lookup"><span data-stu-id="9853b-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="9853b-104">Il <xref:System.Type.IsInstanceOfType%2A> metodo il <xref:System.Type?displayProperty=nameWithType> classe restituisce `True` se la classe specificata eredita dalla classe corrente o se il tipo corrente è un'interfaccia supportata dalla classe specificata.</span><span class="sxs-lookup"><span data-stu-id="9853b-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="9853b-105">Per determinare se un oggetto eredita dalla classe o interfaccia di un altro oggetto</span><span class="sxs-lookup"><span data-stu-id="9853b-105">To determine if one object inherits from another object's class or interface</span></span>  
  
1.  <span data-ttu-id="9853b-106">Per l'oggetto si ritiene che potrebbero essere del tipo di base, richiamare il <xref:System.Object.GetType%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9853b-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>  
  
2.  <span data-ttu-id="9853b-107">Nel <xref:System.Type?displayProperty=nameWithType> oggetto restituito da <xref:System.Object.GetType%2A>, richiamare il <xref:System.Type.IsInstanceOfType%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9853b-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
3.  <span data-ttu-id="9853b-108">Nell'elenco di argomenti per <xref:System.Type.IsInstanceOfType%2A>, specificare l'oggetto si ritiene che potrà essere del tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="9853b-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>  
  
     <span data-ttu-id="9853b-109"><xref:System.Type.IsInstanceOfType%2A> Restituisce `True` se il tipo di argomento eredita il <xref:System.Type?displayProperty=nameWithType> tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="9853b-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9853b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="9853b-110">Example</span></span>  
 <span data-ttu-id="9853b-111">Nell'esempio seguente determina se un oggetto rappresenta una classe derivata dalla classe dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9853b-111">The following example determines whether one object represents a class derived from another object's class.</span></span>  
  
```  
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
  
 <span data-ttu-id="9853b-112">Si noti la posizione imprevista delle due variabili oggetto nella chiamata a <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="9853b-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="9853b-113">Il tipo base previsto viene utilizzato per generare il <xref:System.Type?displayProperty=nameWithType> classe e il tipo derivato previsto viene passata come argomento per il <xref:System.Type.IsInstanceOfType%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9853b-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9853b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9853b-114">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.IsInstanceOfType%2A>  
 [<span data-ttu-id="9853b-115">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="9853b-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="9853b-116">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="9853b-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="9853b-117">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="9853b-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="9853b-118">Procedura: determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="9853b-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
