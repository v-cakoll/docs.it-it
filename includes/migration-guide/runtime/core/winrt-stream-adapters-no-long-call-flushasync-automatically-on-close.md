---
ms.openlocfilehash: 60937459b6f18e9abae87ad2dc97c3942325eedc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620274"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="98518-101">Gli adattatori flusso di WinRT non chiamano più automaticamente FlushAsync alla chiusura</span><span class="sxs-lookup"><span data-stu-id="98518-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="98518-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="98518-102">Details</span></span>

<span data-ttu-id="98518-103">Nelle app di Windows Store, gli adattatori flusso di Windows Runtime non chiamano più il metodo FlushAsync dal metodo Dispose.</span><span class="sxs-lookup"><span data-stu-id="98518-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="98518-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="98518-104">Suggestion</span></span>

<span data-ttu-id="98518-105">Questa modifica dovrebbe essere trasparente.</span><span class="sxs-lookup"><span data-stu-id="98518-105">This change should be transparent.</span></span> <span data-ttu-id="98518-106">Gli sviluppatori potranno ripristinare il comportamento precedente scrivendo del codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="98518-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="98518-107">Nome</span><span class="sxs-lookup"><span data-stu-id="98518-107">Name</span></span>    | <span data-ttu-id="98518-108">Valore</span><span class="sxs-lookup"><span data-stu-id="98518-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="98518-109">Scope</span><span class="sxs-lookup"><span data-stu-id="98518-109">Scope</span></span>   |<span data-ttu-id="98518-110">Modalità trasparente</span><span class="sxs-lookup"><span data-stu-id="98518-110">Transparent</span></span>|
|<span data-ttu-id="98518-111">Version</span><span class="sxs-lookup"><span data-stu-id="98518-111">Version</span></span>|<span data-ttu-id="98518-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="98518-112">4.5.1</span></span>|
|<span data-ttu-id="98518-113">Type</span><span class="sxs-lookup"><span data-stu-id="98518-113">Type</span></span>|<span data-ttu-id="98518-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="98518-114">Runtime</span></span>|
