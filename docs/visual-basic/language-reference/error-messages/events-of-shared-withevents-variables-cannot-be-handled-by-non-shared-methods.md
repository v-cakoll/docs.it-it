---
title: Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: fc163c1069aa6f41766664e0fa5f5a9c34a1f73d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409569"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="d7df9-102">Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi</span><span class="sxs-lookup"><span data-stu-id="d7df9-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="d7df9-103">Una variabile dichiarata con il `Shared` modificatore è una variabile condivisa.</span><span class="sxs-lookup"><span data-stu-id="d7df9-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="d7df9-104">Una variabile condivisa identifica esattamente un percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d7df9-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="d7df9-105">Una variabile dichiarata con il `WithEvents` modificatore dichiara che il tipo a cui appartiene la variabile gestisce il set di eventi generato dalla variabile.</span><span class="sxs-lookup"><span data-stu-id="d7df9-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="d7df9-106">Quando un valore viene assegnato alla variabile, la proprietà creata dalla `WithEvents` dichiarazione sgancia qualsiasi gestore eventi esistente e associa il nuovo gestore eventi tramite il `Add` metodo.</span><span class="sxs-lookup"><span data-stu-id="d7df9-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="d7df9-107">**ID errore:** BC30594</span><span class="sxs-lookup"><span data-stu-id="d7df9-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d7df9-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d7df9-108">To correct this error</span></span>  
  
- <span data-ttu-id="d7df9-109">Dichiarare il gestore dell'evento `Shared` .</span><span class="sxs-lookup"><span data-stu-id="d7df9-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7df9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7df9-110">See also</span></span>

- [<span data-ttu-id="d7df9-111">Condivisa</span><span class="sxs-lookup"><span data-stu-id="d7df9-111">Shared</span></span>](../modifiers/shared.md)
- [<span data-ttu-id="d7df9-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="d7df9-112">WithEvents</span></span>](../modifiers/withevents.md)
