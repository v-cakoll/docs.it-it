---
ms.openlocfilehash: 71f61f23a8b17459610d253766a99e594f09428e
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760427"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="ab4f6-101">PipeConnection.GetHashAlgorithm in WCF ora usa SHA256</span><span class="sxs-lookup"><span data-stu-id="ab4f6-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ab4f6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ab4f6-102">Details</span></span>|<span data-ttu-id="ab4f6-103">A partire da .NET Framework 4.7.1, Windows Communication Foundation usa un hash SHA256 per generare nomi casuali per le named pipe.</span><span class="sxs-lookup"><span data-stu-id="ab4f6-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="ab4f6-104">In .NET Framework 4.7 e versioni precedenti veniva usato l'hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="ab4f6-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="ab4f6-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ab4f6-105">Suggestion</span></span>|<span data-ttu-id="ab4f6-106">Se si verificano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:</span><span class="sxs-lookup"><span data-stu-id="ab4f6-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="ab4f6-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="ab4f6-107">Scope</span></span>|<span data-ttu-id="ab4f6-108">Secondario</span><span class="sxs-lookup"><span data-stu-id="ab4f6-108">Minor</span></span>|
|<span data-ttu-id="ab4f6-109">Versione</span><span class="sxs-lookup"><span data-stu-id="ab4f6-109">Version</span></span>|<span data-ttu-id="ab4f6-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="ab4f6-110">4.7.1</span></span>|
|<span data-ttu-id="ab4f6-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab4f6-111">Type</span></span>|<span data-ttu-id="ab4f6-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="ab4f6-112">Runtime</span></span>|

