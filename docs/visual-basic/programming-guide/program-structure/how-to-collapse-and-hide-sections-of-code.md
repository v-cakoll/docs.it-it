---
title: 'Procedura: comprimere e nascondere sezioni di codice (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
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
ms.openlocfilehash: 4dcd5cd5d79629fd008534112cb72d5bcfec476e
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="b6e84-102">Procedura: comprimere e nascondere sezioni di codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6e84-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="b6e84-103">Il `#Region` (direttiva) consente di comprimere e nascondere sezioni di codice in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] file.</span><span class="sxs-lookup"><span data-stu-id="b6e84-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files.</span></span> <span data-ttu-id="b6e84-104">Il `#Region` direttiva consente di specificare un blocco di codice che è possibile espandere o comprimere tramite la [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] editor di codice.</span><span class="sxs-lookup"><span data-stu-id="b6e84-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] code editor.</span></span> <span data-ttu-id="b6e84-105">La possibilità di nascondere il codice in modo selettivo rende i file più gestibile e più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="b6e84-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="b6e84-106">Per altre informazioni, vedere [Struttura](https://docs.microsoft.com/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="b6e84-106">For more information, see [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="b6e84-107">`#Region`direttive supportano la semantica dei blocchi di codice, ad esempio `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="b6e84-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="b6e84-108">Ciò significa che non possono iniziare in un blocco e terminare con un altro. l'inizio e fine deve essere nello stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="b6e84-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="b6e84-109">`#Region`le direttive non sono supportate all'interno delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="b6e84-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="b6e84-110">Per comprimere e nascondere una sezione di codice</span><span class="sxs-lookup"><span data-stu-id="b6e84-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="b6e84-111">Inserire la sezione di codice tra le `#Region` e `#End Region` istruzioni, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b6e84-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     <span data-ttu-id="b6e84-112">[!code-vb[6 VbVbalrConditionalComp](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b6e84-112">[!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span></span>  
  
     <span data-ttu-id="b6e84-113">Il `#Region` blocco può essere utilizzato più volte in un file di codice, di conseguenza, gli utenti possono definire i propri blocchi di routine e le classi che possono, a sua volta, essere compressi.</span><span class="sxs-lookup"><span data-stu-id="b6e84-113">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="b6e84-114">`#Region`possono anche essere nidificati all'interno di altri `#Region` blocchi.</span><span class="sxs-lookup"><span data-stu-id="b6e84-114">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b6e84-115">Nascondere il codice non impedisce che venga compilato e non influisce sulla `#If...#End If` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="b6e84-115">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e84-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6e84-116">See Also</span></span>  
 <span data-ttu-id="b6e84-117">[Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="b6e84-117">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>  
<span data-ttu-id="b6e84-118"> [#Region (direttiva)](../../../visual-basic/language-reference/directives/region-directive.md) </span><span class="sxs-lookup"><span data-stu-id="b6e84-118"> [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) </span></span>  
<span data-ttu-id="b6e84-119"> [#If... Then... #Else direttive](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="b6e84-119"> [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="b6e84-120"> [Struttura](https://docs.microsoft.com/visualstudio/ide/outlining)</span><span class="sxs-lookup"><span data-stu-id="b6e84-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining)</span></span>
