---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235625"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="e4349-101">Gli adattatori flusso di WinRT non chiamano più automaticamente FlushAsync alla chiusura</span><span class="sxs-lookup"><span data-stu-id="e4349-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e4349-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e4349-102">Details</span></span>|<span data-ttu-id="e4349-103">Nelle app di Windows Store, gli adattatori flusso di Windows Runtime non chiamano più il metodo FlushAsync dal metodo Dispose.</span><span class="sxs-lookup"><span data-stu-id="e4349-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>|
|<span data-ttu-id="e4349-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="e4349-104">Suggestion</span></span>|<span data-ttu-id="e4349-105">Questa modifica dovrebbe essere trasparente.</span><span class="sxs-lookup"><span data-stu-id="e4349-105">This change should be transparent.</span></span> <span data-ttu-id="e4349-106">Gli sviluppatori potranno ripristinare il comportamento precedente scrivendo del codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e4349-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|<span data-ttu-id="e4349-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="e4349-107">Scope</span></span>|<span data-ttu-id="e4349-108">Trasparente</span><span class="sxs-lookup"><span data-stu-id="e4349-108">Transparent</span></span>|
|<span data-ttu-id="e4349-109">Versione</span><span class="sxs-lookup"><span data-stu-id="e4349-109">Version</span></span>|<span data-ttu-id="e4349-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="e4349-110">4.5.1</span></span>|
|<span data-ttu-id="e4349-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="e4349-111">Type</span></span>|<span data-ttu-id="e4349-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="e4349-112">Runtime</span></span>|
