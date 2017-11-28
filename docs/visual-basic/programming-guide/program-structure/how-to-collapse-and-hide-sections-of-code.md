---
title: 'Procedura: comprimere e nascondere sezioni di codice (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56a31f0c8af9b84e87ebe1e5191d72d19be8340f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="ffa24-102">Procedura: comprimere e nascondere sezioni di codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffa24-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="ffa24-103">Il `#Region` direttiva consente di comprimere e nascondere sezioni di codice in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] file.</span><span class="sxs-lookup"><span data-stu-id="ffa24-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files.</span></span> <span data-ttu-id="ffa24-104">Il `#Region` direttiva consente di specificare un blocco di codice che è possibile espandere o comprimere tramite la [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] editor di codice.</span><span class="sxs-lookup"><span data-stu-id="ffa24-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] code editor.</span></span> <span data-ttu-id="ffa24-105">La possibilità di nascondere in modo selettivo il codice rende i file più gestibile e più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="ffa24-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="ffa24-106">Per altre informazioni, vedere [Struttura](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="ffa24-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="ffa24-107">`#Region`direttive supportano la semantica dei blocchi di codice, ad esempio `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="ffa24-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="ffa24-108">Ciò significa che non possono iniziare in un blocco e terminare con un altro. inizio e fine deve essere nello stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="ffa24-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="ffa24-109">`#Region`direttive non sono supportate all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="ffa24-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="ffa24-110">Per comprimere e nascondere una sezione di codice</span><span class="sxs-lookup"><span data-stu-id="ffa24-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="ffa24-111">Inserire la sezione di codice tra le `#Region` e `#End Region` istruzioni, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ffa24-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     <span data-ttu-id="ffa24-112">Il `#Region` blocco può essere utilizzato più volte in un file di codice; pertanto, gli utenti possono definire i propri blocchi di routine e le classi che a sua volta, possono essere compressi.</span><span class="sxs-lookup"><span data-stu-id="ffa24-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="ffa24-113">`#Region`blocchi possono anche essere annidati all'interno di altri `#Region` blocchi.</span><span class="sxs-lookup"><span data-stu-id="ffa24-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ffa24-114">Nascondere il codice non impedisce che venga compilato e non influisce sulla `#If...#End If` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="ffa24-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa24-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffa24-115">See Also</span></span>  
 [<span data-ttu-id="ffa24-116">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="ffa24-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="ffa24-117">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="ffa24-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="ffa24-118">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="ffa24-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="ffa24-119">Struttura</span><span class="sxs-lookup"><span data-stu-id="ffa24-119">Outlining</span></span>](/visualstudio/ide/outlining)
