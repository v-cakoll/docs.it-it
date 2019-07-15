---
ms.openlocfilehash: c1a2d76b4e596acc395da6cefed008078e57a336
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858601"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="a968e-101">I valori di unione Null non risultano visibili nel debugger fino al passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a968e-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a968e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a968e-102">Details</span></span>|<span data-ttu-id="a968e-103">A causa di un bug in .NET Framework 4.5, i valori impostati tramite un'operazione di unione Null non sono visibili nel debugger immediatamente dopo l'esecuzione dell'operazione di assegnazione quando si usa la versione a 64 bit del framework.</span><span class="sxs-lookup"><span data-stu-id="a968e-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="a968e-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="a968e-104">Suggestion</span></span>|<span data-ttu-id="a968e-105">L'esecuzione di un ulteriore passo nel debugger determinerà il corretto aggiornamento del valore locale o del valore del campo.</span><span class="sxs-lookup"><span data-stu-id="a968e-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="a968e-106">Questo problema è stato corretto in .NET Framework 4.6. L'aggiornamento a questa versione del framework dovrebbe quindi risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="a968e-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="a968e-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="a968e-107">Scope</span></span>|<span data-ttu-id="a968e-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a968e-108">Edge</span></span>|
|<span data-ttu-id="a968e-109">Versione</span><span class="sxs-lookup"><span data-stu-id="a968e-109">Version</span></span>|<span data-ttu-id="a968e-110">4.5</span><span class="sxs-lookup"><span data-stu-id="a968e-110">4.5</span></span>|
|<span data-ttu-id="a968e-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="a968e-111">Type</span></span>|<span data-ttu-id="a968e-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="a968e-112">Runtime</span></span>|

