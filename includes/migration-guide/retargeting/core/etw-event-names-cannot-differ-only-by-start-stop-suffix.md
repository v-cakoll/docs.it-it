---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614456"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="518d1-101">I nomi di eventi ETW non possono essere diversi solo per il suffisso "Start" o "Stop"</span><span class="sxs-lookup"><span data-stu-id="518d1-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

#### <a name="details"></a><span data-ttu-id="518d1-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="518d1-102">Details</span></span>

<span data-ttu-id="518d1-103">Nel .NET Framework 4,6 e 4.6.1, il runtime genera un'eccezione <xref:System.ArgumentException> quando due Event Tracing for Windows (ETW) si differenziano solo per un suffisso "Start" o "Stop", ad esempio quando un evento è denominato `LogUser` e un altro è denominato `LogUserStart` .</span><span class="sxs-lookup"><span data-stu-id="518d1-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a "Start" or "Stop" suffix (as when one event is named `LogUser` and another is named `LogUserStart`).</span></span> <span data-ttu-id="518d1-104">In questo caso, il runtime non può creare l'origine dell'evento, quindi non viene generata alcuna registrazione.</span><span class="sxs-lookup"><span data-stu-id="518d1-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="518d1-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="518d1-105">Suggestion</span></span>

<span data-ttu-id="518d1-106">Per evitare l'eccezione, assicurarsi che non siano presenti due nomi di evento diversi solo per il suffisso "Start" o "Stop". Questo requisito viene rimosso a partire da .NET Framework 4.6.2; il runtime può evitare ambiguità tra i nomi di evento che differiscono solo per il suffisso "Start" e "Stop".</span><span class="sxs-lookup"><span data-stu-id="518d1-106">To prevent the exception, ensure that no two event names differ only by a "Start" or "Stop" suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the "Start" and "Stop" suffix.</span></span>

| <span data-ttu-id="518d1-107">Nome</span><span class="sxs-lookup"><span data-stu-id="518d1-107">Name</span></span>    | <span data-ttu-id="518d1-108">Valore</span><span class="sxs-lookup"><span data-stu-id="518d1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="518d1-109">Scope</span><span class="sxs-lookup"><span data-stu-id="518d1-109">Scope</span></span>   | <span data-ttu-id="518d1-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="518d1-110">Edge</span></span>        |
| <span data-ttu-id="518d1-111">Version</span><span class="sxs-lookup"><span data-stu-id="518d1-111">Version</span></span> | <span data-ttu-id="518d1-112">4.6</span><span class="sxs-lookup"><span data-stu-id="518d1-112">4.6</span></span>         |
| <span data-ttu-id="518d1-113">Type</span><span class="sxs-lookup"><span data-stu-id="518d1-113">Type</span></span>    | <span data-ttu-id="518d1-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="518d1-114">Retargeting</span></span> |
