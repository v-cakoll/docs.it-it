---
title: Set non supportato in fase di esecuzione
ms.date: 07/20/2015
f1_keywords:
- vbrID382
ms.assetid: cb7285d3-778f-423d-a2be-88573be8ad48
ms.openlocfilehash: 1b3f8aa3811baae240e6baa546082d0dcf2cf667
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325865"
---
# <a name="set-not-supported-at-run-time"></a><span data-ttu-id="3c5ce-102">Set non supportato in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="3c5ce-102">Set not supported at run time</span></span>
<span data-ttu-id="3c5ce-103">Si è provato a impostare o modificare una proprietà il cui valore può essere impostato solo in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3c5ce-103">You tried to set or change a property whose value can only be set at design time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3c5ce-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3c5ce-104">To correct this error</span></span>  
  
1. <span data-ttu-id="3c5ce-105">Rimuovere il riferimento alla proprietà dal codice.</span><span class="sxs-lookup"><span data-stu-id="3c5ce-105">Remove the reference to the property from your code.</span></span>  
  
2. <span data-ttu-id="3c5ce-106">Modificare il riferimento per restituire solo il valore della proprietà in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3c5ce-106">Change the reference to only return the value of the property at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5ce-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c5ce-107">See also</span></span>

- [<span data-ttu-id="3c5ce-108">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="3c5ce-108">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
