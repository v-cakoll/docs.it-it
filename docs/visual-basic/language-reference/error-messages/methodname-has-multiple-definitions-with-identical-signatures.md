---
title: Il metodo '<methodname>' contiene più definizioni con firme identiche
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: fe8d1d8e11e25bcd79894ed82a57dd06748c3d68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920900"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="87c4a-102">'\<NomeMetodo >' contiene più definizioni con firme identiche</span><span class="sxs-lookup"><span data-stu-id="87c4a-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="87c4a-103">Oggetto `Function` o `Sub` dichiarazione di routine Usa la procedura identico nome ed elenco di argomenti come una dichiarazione precedente.</span><span class="sxs-lookup"><span data-stu-id="87c4a-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="87c4a-104">Una possibile causa è un tentativo di eseguire l'overload di routine originale.</span><span class="sxs-lookup"><span data-stu-id="87c4a-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="87c4a-105">Le routine di overload devono avere gli elenchi di argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="87c4a-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="87c4a-106">**ID errore:** BC30269</span><span class="sxs-lookup"><span data-stu-id="87c4a-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="87c4a-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="87c4a-107">To correct this error</span></span>  
  
- <span data-ttu-id="87c4a-108">Modificare il nome della routine o l'elenco di argomenti oppure rimuovere la dichiarazione duplicata.</span><span class="sxs-lookup"><span data-stu-id="87c4a-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c4a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87c4a-109">See also</span></span>

- [<span data-ttu-id="87c4a-110">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="87c4a-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="87c4a-111">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="87c4a-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
