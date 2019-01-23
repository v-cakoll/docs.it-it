---
title: Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 09f56d340322ee88afc54e7e8a53716777782d47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505770"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="b839a-102">Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi</span><span class="sxs-lookup"><span data-stu-id="b839a-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="b839a-103">Una variabile dichiarata con la `Shared` modificatore è una variabile condivisa.</span><span class="sxs-lookup"><span data-stu-id="b839a-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="b839a-104">Una variabile condivisa identifica esattamente una posizione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b839a-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="b839a-105">Una variabile dichiarata con la `WithEvents` modificatore asserisce che il tipo a cui appartiene la variabile gestisce il set di eventi genera la variabile.</span><span class="sxs-lookup"><span data-stu-id="b839a-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="b839a-106">Quando viene assegnato un valore alla variabile, la proprietà creata per il `WithEvents` dichiarazione qualsiasi gestore eventi esistente, scollega e collega il nuovo gestore di eventi tramite il `Add` (metodo).</span><span class="sxs-lookup"><span data-stu-id="b839a-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="b839a-107">**ID errore:** BC30594</span><span class="sxs-lookup"><span data-stu-id="b839a-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b839a-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b839a-108">To correct this error</span></span>  
  
-   <span data-ttu-id="b839a-109">Dichiarare il gestore eventi `Shared`.</span><span class="sxs-lookup"><span data-stu-id="b839a-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b839a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b839a-110">See also</span></span>
- [<span data-ttu-id="b839a-111">Shared</span><span class="sxs-lookup"><span data-stu-id="b839a-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="b839a-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="b839a-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
