---
title: L'espressione chiama in modo ricorsivo la proprietà '<propertyname>' che la contiene
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 42177f22e632e4a05b1f0b4d934f3e56ab9ff0f2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698572"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="943ff-102">L'espressione chiama in modo ricorsivo la proprietà' \<propertyname >' che lo contiene</span><span class="sxs-lookup"><span data-stu-id="943ff-102">Expression recursively calls the containing property '\<propertyname>'</span></span>
<span data-ttu-id="943ff-103">Un'istruzione nella procedura `Set` di una definizione di proprietà archivia un valore nel nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="943ff-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="943ff-104">L'approccio consigliato per contenere il valore di una proprietà consiste nel definire una variabile `Private` nel contenitore della proprietà e usarla nelle procedure `Get` e `Set`.</span><span class="sxs-lookup"><span data-stu-id="943ff-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="943ff-105">La procedura `Set` deve quindi archiviare il valore in ingresso in questa variabile `Private`.</span><span class="sxs-lookup"><span data-stu-id="943ff-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="943ff-106">La procedura `Get` si comporta come una procedura `Function`, in modo da poter assegnare un valore al nome della proprietà e restituire il controllo mediante l'istruzione `End Get`.</span><span class="sxs-lookup"><span data-stu-id="943ff-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="943ff-107">Tuttavia, l'approccio consigliato consiste nell'includere la variabile `Private` come valore in un' [istruzione return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="943ff-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="943ff-108">La procedura `Set` si comporta come una procedura `Sub`, che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="943ff-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="943ff-109">Pertanto, il nome della procedura o della proprietà non ha un significato speciale in una procedura `Set` e non è possibile archiviarvi un valore.</span><span class="sxs-lookup"><span data-stu-id="943ff-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="943ff-110">Nell'esempio seguente viene illustrato l'approccio che può causare questo errore, seguito dall'approccio consigliato.</span><span class="sxs-lookup"><span data-stu-id="943ff-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```vb  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 <span data-ttu-id="943ff-111">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="943ff-111">By default, this message is a warning.</span></span> <span data-ttu-id="943ff-112">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="943ff-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="943ff-113">**ID errore:** BC42026</span><span class="sxs-lookup"><span data-stu-id="943ff-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="943ff-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="943ff-114">To correct this error</span></span>  
  
- <span data-ttu-id="943ff-115">Riscrivere la definizione della proprietà in modo da usare l'approccio consigliato, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="943ff-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943ff-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="943ff-116">See also</span></span>

- [<span data-ttu-id="943ff-117">Routine Property</span><span class="sxs-lookup"><span data-stu-id="943ff-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="943ff-118">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="943ff-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="943ff-119">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="943ff-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
