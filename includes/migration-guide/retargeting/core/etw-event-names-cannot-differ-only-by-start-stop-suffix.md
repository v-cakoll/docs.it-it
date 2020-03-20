---
ms.openlocfilehash: 71c81cf188fa4c2300661f10eb87e7ae00e031f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804487"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="6d079-101">I nomi di eventi ETW non possono essere diversi solo per il suffisso "Start" o "Stop"</span><span class="sxs-lookup"><span data-stu-id="6d079-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6d079-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6d079-102">Details</span></span>|<span data-ttu-id="6d079-103">In .NET Framework 4.6 e 4.6.1 il runtime genera una <xref:System.ArgumentException> quando due nomi di eventi ETW (Event Tracing for Windows) sono diversi solo per il suffisso &quot;Start&quot; o &quot;Stop&quot;, ad esempio quando un evento è denominato <code>LogUser</code> e un altro <code>LogUserStart</code>.</span><span class="sxs-lookup"><span data-stu-id="6d079-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="6d079-104">In questo caso, il runtime non può creare l'origine dell'evento, quindi non viene generata alcuna registrazione.</span><span class="sxs-lookup"><span data-stu-id="6d079-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="6d079-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6d079-105">Suggestion</span></span>|<span data-ttu-id="6d079-106">Per evitare l'eccezione, assicurarsi che non siano presenti nomi di evento che differiscono solo per il suffisso &quot;Start&quot; oppure &quot;Stop&quot;. Questo requisito è stato rimosso a rimosso a partire da .NET Framework 4.6.2 e il runtime può risolvere l'ambiguità di nomi di evento che differiscono solo per il suffisso &quot;Start&quot; e &quot;Stop&quot;.</span><span class="sxs-lookup"><span data-stu-id="6d079-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="6d079-107">Scope</span><span class="sxs-lookup"><span data-stu-id="6d079-107">Scope</span></span>|<span data-ttu-id="6d079-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6d079-108">Edge</span></span>|
|<span data-ttu-id="6d079-109">Versione</span><span class="sxs-lookup"><span data-stu-id="6d079-109">Version</span></span>|<span data-ttu-id="6d079-110">4.6</span><span class="sxs-lookup"><span data-stu-id="6d079-110">4.6</span></span>|
|<span data-ttu-id="6d079-111">Type</span><span class="sxs-lookup"><span data-stu-id="6d079-111">Type</span></span>|<span data-ttu-id="6d079-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="6d079-112">Retargeting</span></span>|
