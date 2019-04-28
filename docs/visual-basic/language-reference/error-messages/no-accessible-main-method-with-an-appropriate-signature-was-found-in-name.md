---
title: Impossibile trovare in '<name>' un metodo 'Main' accessibile con una firma appropriata
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: f5053bddf4b9ba791ad6d0733e1dd89c4ded91bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918268"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="d20ec-102">È stato trovato alcun metodo 'Main' accessibile con una firma appropriata '\<nome >'</span><span class="sxs-lookup"><span data-stu-id="d20ec-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="d20ec-103">Le applicazioni della riga di comando devono avere un `Sub Main` definito.</span><span class="sxs-lookup"><span data-stu-id="d20ec-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="d20ec-104">`Main` deve essere dichiarato come `Public Shared` se è definito in una classe o come `Public` se definita in un modulo.</span><span class="sxs-lookup"><span data-stu-id="d20ec-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="d20ec-105">**ID errore:** BC30737</span><span class="sxs-lookup"><span data-stu-id="d20ec-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d20ec-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d20ec-106">To correct this error</span></span>  
  
- <span data-ttu-id="d20ec-107">Definire un `Public Sub Main` procedure per il progetto.</span><span class="sxs-lookup"><span data-stu-id="d20ec-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="d20ec-108">Dichiara la classe come `Shared` se e solo se viene definita in una classe.</span><span class="sxs-lookup"><span data-stu-id="d20ec-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d20ec-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d20ec-109">See also</span></span>

- [<span data-ttu-id="d20ec-110">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d20ec-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="d20ec-111">Routine</span><span class="sxs-lookup"><span data-stu-id="d20ec-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
