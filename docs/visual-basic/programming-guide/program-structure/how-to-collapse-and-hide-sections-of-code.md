---
title: 'Procedura: Comprimere e nascondere sezioni di codice (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 367527fd638f6855077caf8ff5911edb333dfcbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648773"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="06594-102">Procedura: Comprimere e nascondere sezioni di codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06594-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="06594-103">Il `#Region` direttiva consente di comprimere e nascondere sezioni di codice nel file di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="06594-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="06594-104">Il `#Region` direttiva consente di specificare un blocco di codice che è possibile espandere o comprimere quando si usa l'editor di Visual Studio code.</span><span class="sxs-lookup"><span data-stu-id="06594-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="06594-105">La possibilità di nascondere in modo selettivo il codice rende i file più gestibile e più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="06594-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="06594-106">Per altre informazioni, vedere [Struttura](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="06594-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="06594-107">`#Region` direttive supportano la semantica di blocco di codice, ad esempio `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="06594-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="06594-108">Ciò significa che non possono iniziare in un blocco e terminare con un altro. l'inizio e fine deve essere nello stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="06594-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="06594-109">`#Region` direttive non sono supportate all'interno delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="06594-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="06594-110">Per comprimere e nascondere una sezione di codice</span><span class="sxs-lookup"><span data-stu-id="06594-110">To collapse and hide a section of code</span></span>  
  
- <span data-ttu-id="06594-111">Inserire la sezione di codice tra il `#Region` e `#End Region` (istruzioni), come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="06594-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     <span data-ttu-id="06594-112">Il `#Region` blocco può essere usato più volte in un file di codice, di conseguenza, gli utenti possono definire i propri blocchi di procedure e le classi che a sua volta, possono essere compressi.</span><span class="sxs-lookup"><span data-stu-id="06594-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="06594-113">`#Region` blocchi possono anche essere annidati all'interno di altri `#Region` blocchi.</span><span class="sxs-lookup"><span data-stu-id="06594-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="06594-114">Nascondere il codice non impedisce che venga compilato e non influisce sul `#If...#End If` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="06594-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06594-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06594-115">See also</span></span>

- [<span data-ttu-id="06594-116">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="06594-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="06594-117">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="06594-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="06594-118">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="06594-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="06594-119">Struttura</span><span class="sxs-lookup"><span data-stu-id="06594-119">Outlining</span></span>](/visualstudio/ide/outlining)
