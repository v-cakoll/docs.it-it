---
title: '&#39;Modulo&#39; istruzioni possono trovarsi solo a livello di file o lo spazio dei nomi'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bdbf8df5942e9df4b9696aeea4e3492121efe21a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746312"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="5a199-102">&#39;Modulo&#39; istruzioni possono trovarsi solo a livello di file o lo spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="5a199-102">&#39;Module&#39; statements can occur only at file or namespace level</span></span>
<span data-ttu-id="5a199-103">`Module` devono essere visualizzate nella parte superiore del file di origine immediatamente dopo aver `Option` e `Imports` istruzioni, gli attributi globali e le dichiarazioni dello spazio dei nomi, ma prima di tutte le altre dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="5a199-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="5a199-104">**ID errore:** BC30617</span><span class="sxs-lookup"><span data-stu-id="5a199-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a199-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5a199-105">To correct this error</span></span>  
  
-   <span data-ttu-id="5a199-106">Spostare l'istruzione `Module` all'inizio della dichiarazione dello spazio dei nomi o del file di origine.</span><span class="sxs-lookup"><span data-stu-id="5a199-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a199-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a199-107">See also</span></span>
- [<span data-ttu-id="5a199-108">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="5a199-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
