---
title: Il metodo '<methodname>' contiene più definizioni con firme identiche
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 3b397711cc2fb1fd0c1dfd76899b162ab5fc1542
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397233"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="a5bf1-102">Il metodo '\<methodname>' contiene più definizioni con firme identiche</span><span class="sxs-lookup"><span data-stu-id="a5bf1-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="a5bf1-103">Una `Function` `Sub` dichiarazione di routine o usa il nome della procedura e l'elenco di argomenti identici di una dichiarazione precedente.</span><span class="sxs-lookup"><span data-stu-id="a5bf1-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="a5bf1-104">Una delle possibili cause è il tentativo di eseguire l'overload della routine originale.</span><span class="sxs-lookup"><span data-stu-id="a5bf1-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="a5bf1-105">Le routine di overload devono contenere elenchi di argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="a5bf1-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="a5bf1-106">**ID errore:** BC30269</span><span class="sxs-lookup"><span data-stu-id="a5bf1-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a5bf1-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a5bf1-107">To correct this error</span></span>  
  
- <span data-ttu-id="a5bf1-108">Modificare il nome della stored procedure o l'elenco degli argomenti oppure rimuovere la dichiarazione duplicata.</span><span class="sxs-lookup"><span data-stu-id="a5bf1-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5bf1-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5bf1-109">See also</span></span>

- [<span data-ttu-id="a5bf1-110">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="a5bf1-110">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="a5bf1-111">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="a5bf1-111">Considerations in Overloading Procedures</span></span>](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
