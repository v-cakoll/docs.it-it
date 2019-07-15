---
ms.openlocfilehash: 43e9c1c2f03daedf4d56152da5672b89399a3c69
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804652"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="1ebf6-101">VB.NET non supporta più la qualificazione parziale dello spazio dei nomi per le API System.Windows</span><span class="sxs-lookup"><span data-stu-id="1ebf6-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1ebf6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1ebf6-102">Details</span></span>|<span data-ttu-id="1ebf6-103">A partire da .NET Framework 4.5.2, i progetti VB.NET non possono specificare API System.Windows con spazi dei nomi parzialmente qualificati.</span><span class="sxs-lookup"><span data-stu-id="1ebf6-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="1ebf6-104">Ad esempio, un riferimento a <code>Windows.Forms.DialogResult</code> avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1ebf6-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="1ebf6-105">Il codice deve invece fare riferimento al nome completo (<xref:System.Windows.Forms.DialogResult>) o importare lo spazio dei nomi specifico e fare semplicemente riferimento a <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="1ebf6-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="1ebf6-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1ebf6-106">Suggestion</span></span>|<span data-ttu-id="1ebf6-107">È consigliabile aggiornare il codice in modo che faccia riferimento alle API <code>System.Windows</code> tramite nomi semplici (e importare lo spazio dei nomi rilevante) o con nomi completi.</span><span class="sxs-lookup"><span data-stu-id="1ebf6-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="1ebf6-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="1ebf6-108">Scope</span></span>|<span data-ttu-id="1ebf6-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="1ebf6-109">Minor</span></span>|
|<span data-ttu-id="1ebf6-110">Versione</span><span class="sxs-lookup"><span data-stu-id="1ebf6-110">Version</span></span>|<span data-ttu-id="1ebf6-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="1ebf6-111">4.5.2</span></span>|
|<span data-ttu-id="1ebf6-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="1ebf6-112">Type</span></span>|<span data-ttu-id="1ebf6-113">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="1ebf6-113">Retargeting</span></span>|

