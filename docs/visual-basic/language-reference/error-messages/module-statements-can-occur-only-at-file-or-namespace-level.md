---
title: Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: d01c30571fc34e142300ac8706c56d5e99175fcf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397207"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="123aa-102">Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="123aa-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="123aa-103">`Module`le istruzioni devono essere visualizzate nella parte superiore del file di origine immediatamente dopo `Option` `Imports` le istruzioni and, gli attributi globali e le dichiarazioni dello spazio dei nomi, ma prima di tutte le altre dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="123aa-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="123aa-104">**ID errore:** BC30617</span><span class="sxs-lookup"><span data-stu-id="123aa-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="123aa-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="123aa-105">To correct this error</span></span>  
  
- <span data-ttu-id="123aa-106">Spostare l'istruzione `Module` all'inizio della dichiarazione dello spazio dei nomi o del file di origine.</span><span class="sxs-lookup"><span data-stu-id="123aa-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123aa-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="123aa-107">See also</span></span>

- [<span data-ttu-id="123aa-108">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="123aa-108">Module Statement</span></span>](../statements/module-statement.md)
