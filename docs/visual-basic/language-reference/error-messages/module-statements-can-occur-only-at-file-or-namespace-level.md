---
title: Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bf0239422fb5a98e4670aea407f684753d3a7ea4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825443"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="d5cc9-102">Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d5cc9-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="d5cc9-103">`Module` devono essere visualizzate nella parte superiore del file di origine immediatamente dopo aver `Option` e `Imports` istruzioni, gli attributi globali e le dichiarazioni dello spazio dei nomi, ma prima di tutte le altre dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="d5cc9-104">**ID errore:** BC30617</span><span class="sxs-lookup"><span data-stu-id="d5cc9-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5cc9-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d5cc9-105">To correct this error</span></span>  
  
-   <span data-ttu-id="d5cc9-106">Spostare l'istruzione `Module` all'inizio della dichiarazione dello spazio dei nomi o del file di origine.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5cc9-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5cc9-107">See also</span></span>

- [<span data-ttu-id="d5cc9-108">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="d5cc9-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
