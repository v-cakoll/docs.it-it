---
title: '&#39;&lt;MethodName&gt; &#39; contiene più definizioni con firme identiche'
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: daa1bc4fcc3ee0fe0279a029f9aac03d4555d582
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536945"
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="f6d93-102">&#39;&lt;MethodName&gt; &#39; contiene più definizioni con firme identiche</span><span class="sxs-lookup"><span data-stu-id="f6d93-102">&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures</span></span>
<span data-ttu-id="f6d93-103">Oggetto `Function` o `Sub` dichiarazione di routine Usa la procedura identico nome ed elenco di argomenti come una dichiarazione precedente.</span><span class="sxs-lookup"><span data-stu-id="f6d93-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="f6d93-104">Una possibile causa è un tentativo di eseguire l'overload di routine originale.</span><span class="sxs-lookup"><span data-stu-id="f6d93-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="f6d93-105">Le routine di overload devono avere gli elenchi di argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="f6d93-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="f6d93-106">**ID errore:** BC30269</span><span class="sxs-lookup"><span data-stu-id="f6d93-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f6d93-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f6d93-107">To correct this error</span></span>  
  
-   <span data-ttu-id="f6d93-108">Modificare il nome della routine o l'elenco di argomenti oppure rimuovere la dichiarazione duplicata.</span><span class="sxs-lookup"><span data-stu-id="f6d93-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d93-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6d93-109">See also</span></span>
- [<span data-ttu-id="f6d93-110">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="f6d93-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="f6d93-111">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="f6d93-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
