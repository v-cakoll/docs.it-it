---
ms.openlocfilehash: 0f87f9e9b87860da97ce96e18104b44ec4327c91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621232"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="885de-101">PipeConnection.GetHashAlgorithm in WCF ora usa SHA256</span><span class="sxs-lookup"><span data-stu-id="885de-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="885de-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="885de-102">Details</span></span>

<span data-ttu-id="885de-103">A partire da .NET Framework 4.7.1, Windows Communication Foundation usa un hash SHA256 per generare nomi casuali per le named pipe.</span><span class="sxs-lookup"><span data-stu-id="885de-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="885de-104">In .NET Framework 4.7 e versioni precedenti veniva usato l'hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="885de-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="885de-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="885de-105">Suggestion</span></span>

<span data-ttu-id="885de-106">Se si verificano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:</span><span class="sxs-lookup"><span data-stu-id="885de-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="885de-107">Nome</span><span class="sxs-lookup"><span data-stu-id="885de-107">Name</span></span>    | <span data-ttu-id="885de-108">Valore</span><span class="sxs-lookup"><span data-stu-id="885de-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="885de-109">Scope</span><span class="sxs-lookup"><span data-stu-id="885de-109">Scope</span></span>   |<span data-ttu-id="885de-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="885de-110">Minor</span></span>|
|<span data-ttu-id="885de-111">Version</span><span class="sxs-lookup"><span data-stu-id="885de-111">Version</span></span>|<span data-ttu-id="885de-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="885de-112">4.7.1</span></span>|
|<span data-ttu-id="885de-113">Type</span><span class="sxs-lookup"><span data-stu-id="885de-113">Type</span></span>|<span data-ttu-id="885de-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="885de-114">Runtime</span></span>|
