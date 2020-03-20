---
ms.openlocfilehash: 3b7309347c643d89a28331c6ef3cac36085a969a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858424"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="a1083-101">Il rendering delle finestre WPF viene eseguito senza ritaglio quando le finestre si estendono oltre un singolo monitor</span><span class="sxs-lookup"><span data-stu-id="a1083-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a1083-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a1083-102">Details</span></span>|<span data-ttu-id="a1083-103">In .NET Framework 4.6 in esecuzione su Windows 8 e versioni successive viene eseguito il rendering dell'intera finestra senza ritaglio quando la finestra si estende al di fuori di un singolo schermo in uno scenario d'uso di più monitor.</span><span class="sxs-lookup"><span data-stu-id="a1083-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="a1083-104">Questo comportamento è diverso rispetto a quello delle versioni precedenti di .NET Framework in cui le finestre WPF che si estendevano oltre un singolo schermo venivano ritagliate.</span><span class="sxs-lookup"><span data-stu-id="a1083-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>|
|<span data-ttu-id="a1083-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="a1083-105">Suggestion</span></span>|<span data-ttu-id="a1083-106">Questo funzionamento (applicazione o non applicazione del ritaglio) può essere impostato esplicitamente tramite l'elemento <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> in <code>&lt;appSettings&gt;</code> nel file di configurazione di un'applicazione oppure impostando la proprietà <code>EnableMultiMonitorDisplayClipping</code> all'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="a1083-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>|
|<span data-ttu-id="a1083-107">Scope</span><span class="sxs-lookup"><span data-stu-id="a1083-107">Scope</span></span>|<span data-ttu-id="a1083-108">Minorenne</span><span class="sxs-lookup"><span data-stu-id="a1083-108">Minor</span></span>|
|<span data-ttu-id="a1083-109">Versione</span><span class="sxs-lookup"><span data-stu-id="a1083-109">Version</span></span>|<span data-ttu-id="a1083-110">4.6</span><span class="sxs-lookup"><span data-stu-id="a1083-110">4.6</span></span>|
|<span data-ttu-id="a1083-111">Type</span><span class="sxs-lookup"><span data-stu-id="a1083-111">Type</span></span>|<span data-ttu-id="a1083-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="a1083-112">Runtime</span></span>|
