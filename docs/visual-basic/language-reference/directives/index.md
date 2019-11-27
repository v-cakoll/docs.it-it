---
title: Direttive
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: d76e10ad5ce8ad3accdc84f97146e0816048d8f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343809"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="fbd4d-102">Direttive (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbd4d-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="fbd4d-103">Gli argomenti in questa sezione descrivono le direttive del compilatore del codice sorgente di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fbd4d-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fbd4d-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fbd4d-104">In This Section</span></span>  

 <span data-ttu-id="fbd4d-105">[Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md) --definire una costante del compilatore</span><span class="sxs-lookup"><span data-stu-id="fbd4d-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="fbd4d-106">[Direttiva #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) : indicare un mapping tra le righe di origine e il testo esterno all'origine</span><span class="sxs-lookup"><span data-stu-id="fbd4d-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="fbd4d-107">[#If... Direttive then... #Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md) : compila i blocchi di codice selezionati</span><span class="sxs-lookup"><span data-stu-id="fbd4d-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="fbd4d-108">[Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md) : comprimere e nascondere sezioni di codice nell'editor di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fbd4d-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="fbd4d-109">**#Disable, #Enable** disabilitare e abilitare avvisi specifici per le aree di codice.</span><span class="sxs-lookup"><span data-stu-id="fbd4d-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="fbd4d-110">È anche possibile disabilitare e abilitare un elenco di codici di avviso delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="fbd4d-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fbd4d-111">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="fbd4d-111">Related Sections</span></span>  

 [<span data-ttu-id="fbd4d-112">Riferimenti per il linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fbd4d-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  
 [<span data-ttu-id="fbd4d-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fbd4d-113">Visual Basic</span></span>](../../../visual-basic/index.md)
