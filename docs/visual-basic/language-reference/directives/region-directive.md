---
title: '#Direttiva Region (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: d0abbdb9cb96ad9977a9af542f90eaad8a7e160e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969713"
---
# <a name="region-directive"></a><span data-ttu-id="8ed6c-102">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="8ed6c-102">#Region Directive</span></span>
<span data-ttu-id="8ed6c-103">Comprime e nasconde sezioni di codice in file di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8ed6c-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ed6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ed6c-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="8ed6c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8ed6c-105">Parts</span></span>  
  
|<span data-ttu-id="8ed6c-106">Termine</span><span class="sxs-lookup"><span data-stu-id="8ed6c-106">Term</span></span>|<span data-ttu-id="8ed6c-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="8ed6c-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="8ed6c-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8ed6c-108">Required.</span></span> <span data-ttu-id="8ed6c-109">Stringa che funge da titolo di un'area quando viene compressa.</span><span class="sxs-lookup"><span data-stu-id="8ed6c-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="8ed6c-110">Le aree sono compresse per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8ed6c-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="8ed6c-111">Termina il blocco `#Region`.</span><span class="sxs-lookup"><span data-stu-id="8ed6c-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ed6c-112">Note</span><span class="sxs-lookup"><span data-stu-id="8ed6c-112">Remarks</span></span>  
 <span data-ttu-id="8ed6c-113">Usare la direttiva `#Region` per specificare un blocco di codice da espandere o comprimere durante l'uso della funzionalità di struttura dell'editor di Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8ed6c-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="8ed6c-114">È possibile inserire, oppure *annidare*, aree all'interno di altre aree per raggruppare aree simili.</span><span class="sxs-lookup"><span data-stu-id="8ed6c-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ed6c-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ed6c-115">Example</span></span>  
 <span data-ttu-id="8ed6c-116">In questo esempio viene usata la direttiva `#Region`.</span><span class="sxs-lookup"><span data-stu-id="8ed6c-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8ed6c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ed6c-117">See also</span></span>
- [<span data-ttu-id="8ed6c-118">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="8ed6c-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="8ed6c-119">Struttura</span><span class="sxs-lookup"><span data-stu-id="8ed6c-119">Outlining</span></span>](/visualstudio/ide/outlining)
- [<span data-ttu-id="8ed6c-120">Procedura: Comprimere e nascondere sezioni di codice</span><span class="sxs-lookup"><span data-stu-id="8ed6c-120">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
