---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857224"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="d24ed-101">Il valore predefinito MsmqSecureHashAlgorithm di WCF è ora SHA256</span><span class="sxs-lookup"><span data-stu-id="d24ed-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d24ed-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d24ed-102">Details</span></span>|<span data-ttu-id="d24ed-103">A partire da .NET Framework 4.7.1 l'algoritmo di firma del messaggio predefinito in WCF per i messaggi Msmq è SHA256.</span><span class="sxs-lookup"><span data-stu-id="d24ed-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="d24ed-104">In .NET Framework 4.7 e versioni precedenti l'algoritmo di firma del messaggio predefinito è SHA1.</span><span class="sxs-lookup"><span data-stu-id="d24ed-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="d24ed-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d24ed-105">Suggestion</span></span>|<span data-ttu-id="d24ed-106">Se si riscontrano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:</span><span class="sxs-lookup"><span data-stu-id="d24ed-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="d24ed-107">Scope</span><span class="sxs-lookup"><span data-stu-id="d24ed-107">Scope</span></span>|<span data-ttu-id="d24ed-108">Minorenne</span><span class="sxs-lookup"><span data-stu-id="d24ed-108">Minor</span></span>|
|<span data-ttu-id="d24ed-109">Versione</span><span class="sxs-lookup"><span data-stu-id="d24ed-109">Version</span></span>|<span data-ttu-id="d24ed-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="d24ed-110">4.7.1</span></span>|
|<span data-ttu-id="d24ed-111">Type</span><span class="sxs-lookup"><span data-stu-id="d24ed-111">Type</span></span>|<span data-ttu-id="d24ed-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="d24ed-112">Runtime</span></span>|
