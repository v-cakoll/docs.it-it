---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804280"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="8feac-101">Gli adattatori flusso di WinRT non chiamano più automaticamente FlushAsync alla chiusura</span><span class="sxs-lookup"><span data-stu-id="8feac-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8feac-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8feac-102">Details</span></span>|<span data-ttu-id="8feac-103">Nelle app di Windows Store, gli adattatori flusso di Windows Runtime non chiamano più il metodo FlushAsync dal metodo Dispose.</span><span class="sxs-lookup"><span data-stu-id="8feac-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>|
|<span data-ttu-id="8feac-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8feac-104">Suggestion</span></span>|<span data-ttu-id="8feac-105">Questa modifica dovrebbe essere trasparente.</span><span class="sxs-lookup"><span data-stu-id="8feac-105">This change should be transparent.</span></span> <span data-ttu-id="8feac-106">Gli sviluppatori potranno ripristinare il comportamento precedente scrivendo del codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8feac-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|<span data-ttu-id="8feac-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="8feac-107">Scope</span></span>|<span data-ttu-id="8feac-108">Trasparente</span><span class="sxs-lookup"><span data-stu-id="8feac-108">Transparent</span></span>|
|<span data-ttu-id="8feac-109">Versione</span><span class="sxs-lookup"><span data-stu-id="8feac-109">Version</span></span>|<span data-ttu-id="8feac-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="8feac-110">4.5.1</span></span>|
|<span data-ttu-id="8feac-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="8feac-111">Type</span></span>|<span data-ttu-id="8feac-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="8feac-112">Runtime</span></span>|
