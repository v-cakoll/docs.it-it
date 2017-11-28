---
title: Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords: BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53372927b88df3946583564492df42170f302739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="293b2-102">Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi</span><span class="sxs-lookup"><span data-stu-id="293b2-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="293b2-103">Una variabile dichiarata con la `Shared` modificatore è una variabile condivisa.</span><span class="sxs-lookup"><span data-stu-id="293b2-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="293b2-104">Una variabile condivisa identifica esattamente una posizione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="293b2-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="293b2-105">Una variabile dichiarata con la `WithEvents` modificatore asserisce che il tipo a cui appartiene la variabile gestisce il set di eventi che genera la variabile.</span><span class="sxs-lookup"><span data-stu-id="293b2-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="293b2-106">Quando viene assegnato un valore alla variabile, la proprietà creato per il `WithEvents` dichiarazione disconnette qualsiasi gestore eventi esistente e associa il nuovo gestore eventi tramite il `Add` metodo.</span><span class="sxs-lookup"><span data-stu-id="293b2-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="293b2-107">**ID errore:** BC30594</span><span class="sxs-lookup"><span data-stu-id="293b2-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="293b2-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="293b2-108">To correct this error</span></span>  
  
-   <span data-ttu-id="293b2-109">Dichiarare il gestore eventi `Shared`.</span><span class="sxs-lookup"><span data-stu-id="293b2-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="293b2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="293b2-110">See Also</span></span>  
 [<span data-ttu-id="293b2-111">Shared</span><span class="sxs-lookup"><span data-stu-id="293b2-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="293b2-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="293b2-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
