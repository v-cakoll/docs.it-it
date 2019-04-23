---
title: Convenzione di chiamata DLL non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: f7b0c3a6edbe0b950195306fa66287ff9b209bfe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306625"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="8ebb0-102">Convenzione di chiamata DLL non valida</span><span class="sxs-lookup"><span data-stu-id="8ebb0-102">Bad DLL calling convention</span></span>
<span data-ttu-id="8ebb0-103">Argomenti passati a una libreria di collegamento dinamico (DLL) devono corrispondere esattamente a quelli previsti per la routine.</span><span class="sxs-lookup"><span data-stu-id="8ebb0-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="8ebb0-104">Convenzioni di chiamata riguardano numero, tipo e ordine degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="8ebb0-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="8ebb0-105">Il programma può chiamare una routine in una DLL che viene passata il tipo non corretto o il numero di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8ebb0-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8ebb0-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8ebb0-106">To correct this error</span></span>  
  
1. <span data-ttu-id="8ebb0-107">Assicurarsi che tutti i tipi di argomenti corrispondano a quelli specificati nella dichiarazione della routine che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="8ebb0-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2. <span data-ttu-id="8ebb0-108">Assicurarsi che si sta passando lo stesso numero di argomenti indicati nella dichiarazione della routine che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="8ebb0-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3. <span data-ttu-id="8ebb0-109">Se la routine di DLL sono previsti argomenti per valore, assicurarsi che `ByVal` specificato per tali argomenti nella dichiarazione della routine.</span><span class="sxs-lookup"><span data-stu-id="8ebb0-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebb0-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ebb0-110">See also</span></span>

- [<span data-ttu-id="8ebb0-111">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="8ebb0-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="8ebb0-112">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="8ebb0-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)
- [<span data-ttu-id="8ebb0-113">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="8ebb0-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
