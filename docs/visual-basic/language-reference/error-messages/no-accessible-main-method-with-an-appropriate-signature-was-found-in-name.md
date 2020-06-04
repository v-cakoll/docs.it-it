---
title: Impossibile trovare in '<name>' un metodo 'Main' accessibile con una firma appropriata
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6760b931ceb2ad5c2c04169d664da8629badc487
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409413"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="c8c00-102">Impossibile trovare in '\<name>' un metodo 'Main' accessibile con una firma appropriata</span><span class="sxs-lookup"><span data-stu-id="c8c00-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="c8c00-103">Per le applicazioni da riga di comando deve essere `Sub Main` definito.</span><span class="sxs-lookup"><span data-stu-id="c8c00-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="c8c00-104">`Main`deve essere dichiarato come `Public Shared` se fosse definito in una classe o come se fosse `Public` definito in un modulo.</span><span class="sxs-lookup"><span data-stu-id="c8c00-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="c8c00-105">**ID errore:** BC30737</span><span class="sxs-lookup"><span data-stu-id="c8c00-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c8c00-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c8c00-106">To correct this error</span></span>  
  
- <span data-ttu-id="c8c00-107">Definire una `Public Sub Main` procedura per il progetto.</span><span class="sxs-lookup"><span data-stu-id="c8c00-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="c8c00-108">Dichiararla come `Shared` se fosse e solo se viene definita all'interno di una classe.</span><span class="sxs-lookup"><span data-stu-id="c8c00-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c00-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8c00-109">See also</span></span>

- [<span data-ttu-id="c8c00-110">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8c00-110">Structure of a Visual Basic Program</span></span>](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="c8c00-111">Procedure</span><span class="sxs-lookup"><span data-stu-id="c8c00-111">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
