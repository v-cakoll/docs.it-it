---
title: 'Procedura: Comprimere e nascondere sezioni di codice'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: c11affe9c4dd4251ba8ff4b87029d314970b5fcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404849"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="909af-102">Procedura: comprimere e nascondere sezioni di codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="909af-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="909af-103">La `#Region` direttiva consente di comprimere e nascondere sezioni di codice in file di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="909af-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="909af-104">La `#Region` direttiva consente di specificare un blocco di codice che è possibile espandere o comprimere quando si usa l'editor di codice di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="909af-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="909af-105">La possibilità di nascondere il codice rende i file più gestibili e più facili da leggere.</span><span class="sxs-lookup"><span data-stu-id="909af-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="909af-106">Per altre informazioni, vedere [Struttura](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="909af-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="909af-107">`#Region`le direttive supportano la semantica del blocco di codice, ad esempio `#If...#End If` .</span><span class="sxs-lookup"><span data-stu-id="909af-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="909af-108">Ciò significa che non possono iniziare in un blocco e terminare con un altro; l'inizio e la fine devono trovarsi nello stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="909af-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="909af-109">`#Region`le direttive non sono supportate all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="909af-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="909af-110">Per comprimere e nascondere una sezione di codice</span><span class="sxs-lookup"><span data-stu-id="909af-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="909af-111">Inserire la sezione di codice tra le `#Region` `#End Region` istruzioni e, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="909af-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="909af-112">Il `#Region` blocco può essere utilizzato più volte in un file di codice; pertanto, gli utenti possono definire blocchi di routine e classi che possono, a loro volta, essere compressi.</span><span class="sxs-lookup"><span data-stu-id="909af-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="909af-113">`#Region`i blocchi possono anche essere annidati all'interno di altri `#Region` blocchi.</span><span class="sxs-lookup"><span data-stu-id="909af-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="909af-114">Il codice nascosto non ne impedisce la compilazione e non influisce sulle `#If...#End If` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="909af-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="909af-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="909af-115">See also</span></span>

- [<span data-ttu-id="909af-116">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="909af-116">Conditional Compilation</span></span>](conditional-compilation.md)
- [<span data-ttu-id="909af-117">#Region (direttiva)</span><span class="sxs-lookup"><span data-stu-id="909af-117">#Region Directive</span></span>](../../language-reference/directives/region-directive.md)
- [<span data-ttu-id="909af-118">#If... Direttive then... #Else</span><span class="sxs-lookup"><span data-stu-id="909af-118">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="909af-119">struttura</span><span class="sxs-lookup"><span data-stu-id="909af-119">Outlining</span></span>](/visualstudio/ide/outlining)
