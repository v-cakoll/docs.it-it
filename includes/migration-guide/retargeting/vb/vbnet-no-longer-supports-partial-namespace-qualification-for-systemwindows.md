---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616077"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="42814-101">VB.NET non supporta più la qualificazione parziale dello spazio dei nomi per le API System.Windows</span><span class="sxs-lookup"><span data-stu-id="42814-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

#### <a name="details"></a><span data-ttu-id="42814-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="42814-102">Details</span></span>

<span data-ttu-id="42814-103">A partire da .NET Framework 4.5.2, i progetti VB.NET non possono specificare API System.Windows con spazi dei nomi parzialmente qualificati.</span><span class="sxs-lookup"><span data-stu-id="42814-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="42814-104">Ad esempio, un riferimento a `Windows.Forms.DialogResult` avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="42814-104">For example, referring to `Windows.Forms.DialogResult` will fail.</span></span> <span data-ttu-id="42814-105">Il codice deve invece fare riferimento al nome completo (<xref:System.Windows.Forms.DialogResult>) o importare lo spazio dei nomi specifico e fare semplicemente riferimento a <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="42814-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="42814-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="42814-106">Suggestion</span></span>

<span data-ttu-id="42814-107">È consigliabile aggiornare il codice in modo che faccia riferimento alle API `System.Windows` tramite nomi semplici (e importare lo spazio dei nomi rilevante) o con nomi completi.</span><span class="sxs-lookup"><span data-stu-id="42814-107">Code should be updated to refer to `System.Windows` APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>

| <span data-ttu-id="42814-108">Nome</span><span class="sxs-lookup"><span data-stu-id="42814-108">Name</span></span>    | <span data-ttu-id="42814-109">Valore</span><span class="sxs-lookup"><span data-stu-id="42814-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="42814-110">Scope</span><span class="sxs-lookup"><span data-stu-id="42814-110">Scope</span></span>   | <span data-ttu-id="42814-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="42814-111">Minor</span></span>       |
| <span data-ttu-id="42814-112">Version</span><span class="sxs-lookup"><span data-stu-id="42814-112">Version</span></span> | <span data-ttu-id="42814-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="42814-113">4.5.2</span></span>       |
| <span data-ttu-id="42814-114">Type</span><span class="sxs-lookup"><span data-stu-id="42814-114">Type</span></span>    | <span data-ttu-id="42814-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="42814-115">Retargeting</span></span> |
