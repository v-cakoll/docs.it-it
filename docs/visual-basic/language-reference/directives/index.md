---
title: Direttive
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5e857198351b30c0d7a38dce1a9e6d1209b5258
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838143"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="24522-102">Direttive (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24522-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="24522-103">Gli argomenti in questa sezione descrivono le direttive del compilatore del codice sorgente di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="24522-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24522-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="24522-104">In This Section</span></span>  

 <span data-ttu-id="24522-105">[Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md) --definire una costante del compilatore</span><span class="sxs-lookup"><span data-stu-id="24522-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="24522-106">[Direttiva #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) : indicare un mapping tra le righe di origine e il testo esterno all'origine</span><span class="sxs-lookup"><span data-stu-id="24522-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="24522-107">[#If... Direttive then... #Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md) : compila i blocchi di codice selezionati</span><span class="sxs-lookup"><span data-stu-id="24522-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="24522-108">[Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md) : comprimere e nascondere sezioni di codice nell'editor di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="24522-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="24522-109">**#Disable, #Enable** disabilitare e abilitare avvisi specifici per le aree di codice.</span><span class="sxs-lookup"><span data-stu-id="24522-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="24522-110">È anche possibile disabilitare e abilitare un elenco di codici di avviso delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="24522-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="24522-111">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="24522-111">Related Sections</span></span>  

 [<span data-ttu-id="24522-112">Riferimenti per il linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24522-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  