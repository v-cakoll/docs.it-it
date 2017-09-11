---
title: '#Region (direttiva) | Documenti di Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
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
ms.openlocfilehash: 86b8e9ce99a8c12e290f5efdc5a5c4da57f350d9
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="region-directive"></a>#<span data-ttu-id="714a8-102">Region (direttiva)</span><span class="sxs-lookup"><span data-stu-id="714a8-102">Region Directive</span></span>
<span data-ttu-id="714a8-103">Comprime e nasconde sezioni di codice in file di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="714a8-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="714a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="714a8-104">Syntax</span></span>  
  
```  
  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="714a8-105">Parti</span><span class="sxs-lookup"><span data-stu-id="714a8-105">Parts</span></span>  
  
|<span data-ttu-id="714a8-106">Termine</span><span class="sxs-lookup"><span data-stu-id="714a8-106">Term</span></span>|<span data-ttu-id="714a8-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="714a8-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="714a8-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="714a8-108">Required.</span></span> <span data-ttu-id="714a8-109">Stringa che funge da titolo di un'area quando viene compressa.</span><span class="sxs-lookup"><span data-stu-id="714a8-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="714a8-110">Le aree sono compresse per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="714a8-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="714a8-111">Termina il blocco `#Region`.</span><span class="sxs-lookup"><span data-stu-id="714a8-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="714a8-112">Note</span><span class="sxs-lookup"><span data-stu-id="714a8-112">Remarks</span></span>  
 <span data-ttu-id="714a8-113">Usare la direttiva `#Region` per specificare un blocco di codice da espandere o comprimere durante l'uso della funzionalità di struttura dell'editor di codice di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="714a8-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="714a8-114">È possibile inserire, o *annidare*, le aree all'interno di altre aree per raggruppare aree simili.</span><span class="sxs-lookup"><span data-stu-id="714a8-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="714a8-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="714a8-115">Example</span></span>  
 <span data-ttu-id="714a8-116">In questo esempio viene usata la direttiva `#Region`.</span><span class="sxs-lookup"><span data-stu-id="714a8-116">This example uses the `#Region` directive.</span></span>  
  
 <span data-ttu-id="714a8-117">[!code-vb[VbVbalrConditionalComp n.&4;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="714a8-117">[!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714a8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="714a8-118">See Also</span></span>  
 <span data-ttu-id="714a8-119">[#If... Then... #Else direttive](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="714a8-119">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="714a8-120"> [Struttura](https://docs.microsoft.com/visualstudio/ide/outlining) </span><span class="sxs-lookup"><span data-stu-id="714a8-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining) </span></span>  
<span data-ttu-id="714a8-121"> [Procedura: Comprimere e nascondere sezioni di codice](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span><span class="sxs-lookup"><span data-stu-id="714a8-121"> [How to: Collapse and Hide Sections of Code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span></span>
