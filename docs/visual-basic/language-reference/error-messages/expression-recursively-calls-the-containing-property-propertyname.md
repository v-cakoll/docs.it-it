---
title: "Espressione in modo ricorsivo chiama la proprietà che contiene &quot;&lt;propertyname&gt;&quot; | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
dev_langs:
- VB
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c7168ab2a2ec5eb0c0d423120b67c10b117c14b2
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a><span data-ttu-id="7b6bd-102">Espressione in modo ricorsivo chiama la proprietà che contiene '&lt;propertyname&gt;'</span><span class="sxs-lookup"><span data-stu-id="7b6bd-102">Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;</span></span>
<span data-ttu-id="7b6bd-103">Un'istruzione all'interno di `Set` routine di una definizione di proprietà archivia un valore nel nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7b6bd-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="7b6bd-104">L'approccio consigliato per contenere il valore di una proprietà consiste nel definire un `Private` variabile nel contenitore della proprietà e utilizzarlo in entrambe le `Get` e `Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="7b6bd-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="7b6bd-105">Il `Set` routine deve archiviare, quindi il valore in ingresso in questa `Private` variabile.</span><span class="sxs-lookup"><span data-stu-id="7b6bd-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="7b6bd-106">Il `Get` routine si comporta come un `Function` procedura per assegnare un valore per il nome della proprietà e restituire il controllo in corrispondenza di `End Get` istruzione.</span><span class="sxs-lookup"><span data-stu-id="7b6bd-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="7b6bd-107">Si consiglia, tuttavia, consiste nell'includere il `Private` variabile come valore in un [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7b6bd-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="7b6bd-108">Il `Set` routine si comporta come un `Sub` routine, che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="7b6bd-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="7b6bd-109">Pertanto, il nome della routine o proprietà hanno alcun significato speciale all'interno di un `Set` ed è possibile archiviare un valore al suo interno.</span><span class="sxs-lookup"><span data-stu-id="7b6bd-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="7b6bd-110">Nell'esempio seguente viene illustrato l'approccio che può causare questo errore, aggiungendo l'approccio consigliato.</span><span class="sxs-lookup"><span data-stu-id="7b6bd-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```  
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
  
 <span data-ttu-id="7b6bd-111">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="7b6bd-111">By default, this message is a warning.</span></span> <span data-ttu-id="7b6bd-112">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7b6bd-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="7b6bd-113">**ID errore:** BC42026</span><span class="sxs-lookup"><span data-stu-id="7b6bd-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7b6bd-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7b6bd-114">To correct this error</span></span>  
  
-   <span data-ttu-id="7b6bd-115">Riscrivere la definizione di proprietà per utilizzare l'approccio consigliato come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="7b6bd-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b6bd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b6bd-116">See Also</span></span>  
 <span data-ttu-id="7b6bd-117">[Proprietà (routine)](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="7b6bd-117">[Property Procedures](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span></span>  
<span data-ttu-id="7b6bd-118"> [Property (istruzione)](../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7b6bd-118"> [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="7b6bd-119"> [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="7b6bd-119"> [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)</span></span>
