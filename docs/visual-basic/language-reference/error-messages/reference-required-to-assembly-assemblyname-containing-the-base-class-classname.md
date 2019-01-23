---
title: Necessario riferimento all'assembly &#39; &lt;assemblyname&gt; &#39; che contiene la classe di base &#39; &lt;classname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: f2aa8f1f05ce15bd25992b7f1851854952108813
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506269"
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a><span data-ttu-id="92294-102">Necessario riferimento all'assembly &#39; &lt;assemblyname&gt; &#39; che contiene la classe di base &#39; &lt;classname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="92294-102">Reference required to assembly &#39;&lt;assemblyname&gt;&#39; containing the base class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="92294-103">Necessario riferimento all'assembly '\<assemblyname >' contenente la classe base\<NomeClasse >'.</span><span class="sxs-lookup"><span data-stu-id="92294-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="92294-104">Aggiungerne uno al progetto.</span><span class="sxs-lookup"><span data-stu-id="92294-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="92294-105">La classe è definita in una libreria a collegamento dinamico (DLL) o in un assembly a cui non si fa direttamente riferimento nel progetto.</span><span class="sxs-lookup"><span data-stu-id="92294-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="92294-106">Il compilatore Visual Basic richiede un riferimento per evitare ambiguità nel caso in cui la classe è definita in più di un file DLL o assembly.</span><span class="sxs-lookup"><span data-stu-id="92294-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="92294-107">**ID errore:** BC30007</span><span class="sxs-lookup"><span data-stu-id="92294-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="92294-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="92294-108">To correct this error</span></span>  
  
-   <span data-ttu-id="92294-109">Includere il nome della DLL o dell'assembly senza riferimento nei riferimenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="92294-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92294-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92294-110">See also</span></span>

- [<span data-ttu-id="92294-111">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="92294-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="92294-112">Risoluzione dei problemi relativi ai riferimenti interrotti</span><span class="sxs-lookup"><span data-stu-id="92294-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
