---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804652"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="fdb35-101">VB.NET non supporta più la qualificazione parziale dello spazio dei nomi per le API System.Windows</span><span class="sxs-lookup"><span data-stu-id="fdb35-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fdb35-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fdb35-102">Details</span></span>|<span data-ttu-id="fdb35-103">A partire da .NET Framework 4.5.2, i progetti VB.NET non possono specificare API System.Windows con spazi dei nomi parzialmente qualificati.</span><span class="sxs-lookup"><span data-stu-id="fdb35-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="fdb35-104">Ad esempio, un riferimento a <code>Windows.Forms.DialogResult</code> avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="fdb35-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="fdb35-105">Il codice deve invece fare riferimento al nome completo (<xref:System.Windows.Forms.DialogResult>) o importare lo spazio dei nomi specifico e fare semplicemente riferimento a <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="fdb35-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="fdb35-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="fdb35-106">Suggestion</span></span>|<span data-ttu-id="fdb35-107">È consigliabile aggiornare il codice in modo che faccia riferimento alle API <code>System.Windows</code> tramite nomi semplici (e importare lo spazio dei nomi rilevante) o con nomi completi.</span><span class="sxs-lookup"><span data-stu-id="fdb35-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="fdb35-108">Scope</span><span class="sxs-lookup"><span data-stu-id="fdb35-108">Scope</span></span>|<span data-ttu-id="fdb35-109">Minorenne</span><span class="sxs-lookup"><span data-stu-id="fdb35-109">Minor</span></span>|
|<span data-ttu-id="fdb35-110">Versione</span><span class="sxs-lookup"><span data-stu-id="fdb35-110">Version</span></span>|<span data-ttu-id="fdb35-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="fdb35-111">4.5.2</span></span>|
|<span data-ttu-id="fdb35-112">Type</span><span class="sxs-lookup"><span data-stu-id="fdb35-112">Type</span></span>|<span data-ttu-id="fdb35-113">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="fdb35-113">Retargeting</span></span>|
