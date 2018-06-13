---
title: '&#39;Modulo&#39; le istruzioni possono trovarsi solo a livello di file o spazio dei nomi'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 53199c2d7081445dc5490d5c54c98f93ee7522eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593165"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="3cb04-102">&#39;Modulo&#39; le istruzioni possono trovarsi solo a livello di file o spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3cb04-102">&#39;Module&#39; statements can occur only at file or namespace level</span></span>
<span data-ttu-id="3cb04-103">`Module` le istruzioni devono essere visualizzati nella parte superiore del file di origine immediatamente dopo `Option` e `Imports` istruzioni, gli attributi globali e le dichiarazioni dello spazio dei nomi, ma prima di tutte le altre dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="3cb04-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="3cb04-104">**ID errore:** BC30617</span><span class="sxs-lookup"><span data-stu-id="3cb04-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3cb04-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3cb04-105">To correct this error</span></span>  
  
-   <span data-ttu-id="3cb04-106">Spostare il `Module` all'inizio del file di origine o di dichiarazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3cb04-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb04-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cb04-107">See Also</span></span>  
 [<span data-ttu-id="3cb04-108">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="3cb04-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
