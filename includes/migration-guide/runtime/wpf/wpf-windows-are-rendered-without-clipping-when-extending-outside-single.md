---
ms.openlocfilehash: d276e2bbf24c8b2389a0a8078c62c327c3729d50
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621355"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="8bf87-101">Il rendering delle finestre WPF viene eseguito senza ritaglio quando le finestre si estendono oltre un singolo monitor</span><span class="sxs-lookup"><span data-stu-id="8bf87-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

#### <a name="details"></a><span data-ttu-id="8bf87-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8bf87-102">Details</span></span>

<span data-ttu-id="8bf87-103">In .NET Framework 4.6 in esecuzione su Windows 8 e versioni successive viene eseguito il rendering dell'intera finestra senza ritaglio quando la finestra si estende al di fuori di un singolo schermo in uno scenario d'uso di più monitor.</span><span class="sxs-lookup"><span data-stu-id="8bf87-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="8bf87-104">Questo comportamento è diverso rispetto a quello delle versioni precedenti di .NET Framework in cui le finestre WPF che si estendevano oltre un singolo schermo venivano ritagliate.</span><span class="sxs-lookup"><span data-stu-id="8bf87-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8bf87-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8bf87-105">Suggestion</span></span>

<span data-ttu-id="8bf87-106">Questo funzionamento (applicazione o non applicazione del ritaglio) può essere impostato esplicitamente tramite l'elemento <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> in <code>&lt;appSettings&gt;</code> nel file di configurazione di un'applicazione oppure impostando la proprietà <code>EnableMultiMonitorDisplayClipping</code> all'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="8bf87-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>

| <span data-ttu-id="8bf87-107">Nome</span><span class="sxs-lookup"><span data-stu-id="8bf87-107">Name</span></span>    | <span data-ttu-id="8bf87-108">Valore</span><span class="sxs-lookup"><span data-stu-id="8bf87-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8bf87-109">Scope</span><span class="sxs-lookup"><span data-stu-id="8bf87-109">Scope</span></span>   |<span data-ttu-id="8bf87-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="8bf87-110">Minor</span></span>|
|<span data-ttu-id="8bf87-111">Version</span><span class="sxs-lookup"><span data-stu-id="8bf87-111">Version</span></span>|<span data-ttu-id="8bf87-112">4.6</span><span class="sxs-lookup"><span data-stu-id="8bf87-112">4.6</span></span>|
|<span data-ttu-id="8bf87-113">Type</span><span class="sxs-lookup"><span data-stu-id="8bf87-113">Type</span></span>|<span data-ttu-id="8bf87-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="8bf87-114">Runtime</span></span>|
