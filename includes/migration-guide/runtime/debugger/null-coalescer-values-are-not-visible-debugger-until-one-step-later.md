---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858601"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="6863f-101">I valori di unione Null non risultano visibili nel debugger fino al passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6863f-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6863f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6863f-102">Details</span></span>|<span data-ttu-id="6863f-103">A causa di un bug in .NET Framework 4.5, i valori impostati tramite un'operazione di unione Null non sono visibili nel debugger immediatamente dopo l'esecuzione dell'operazione di assegnazione quando si usa la versione a 64 bit del framework.</span><span class="sxs-lookup"><span data-stu-id="6863f-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="6863f-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6863f-104">Suggestion</span></span>|<span data-ttu-id="6863f-105">L'esecuzione di un ulteriore passo nel debugger determinerà il corretto aggiornamento del valore locale o del valore del campo.</span><span class="sxs-lookup"><span data-stu-id="6863f-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="6863f-106">Questo problema è stato corretto in .NET Framework 4.6. L'aggiornamento a questa versione del framework dovrebbe quindi risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="6863f-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="6863f-107">Scope</span><span class="sxs-lookup"><span data-stu-id="6863f-107">Scope</span></span>|<span data-ttu-id="6863f-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6863f-108">Edge</span></span>|
|<span data-ttu-id="6863f-109">Versione</span><span class="sxs-lookup"><span data-stu-id="6863f-109">Version</span></span>|<span data-ttu-id="6863f-110">4.5</span><span class="sxs-lookup"><span data-stu-id="6863f-110">4.5</span></span>|
|<span data-ttu-id="6863f-111">Type</span><span class="sxs-lookup"><span data-stu-id="6863f-111">Type</span></span>|<span data-ttu-id="6863f-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="6863f-112">Runtime</span></span>|
