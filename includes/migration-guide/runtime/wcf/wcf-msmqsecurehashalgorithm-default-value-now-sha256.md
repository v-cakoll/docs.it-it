---
ms.openlocfilehash: ccdf232d743c9e270b6ed21f698998eb95a97399
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621220"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="8a851-101">Il valore predefinito MsmqSecureHashAlgorithm di WCF è ora SHA256</span><span class="sxs-lookup"><span data-stu-id="8a851-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="8a851-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8a851-102">Details</span></span>

<span data-ttu-id="8a851-103">A partire da .NET Framework 4.7.1 l'algoritmo di firma del messaggio predefinito in WCF per i messaggi Msmq è SHA256.</span><span class="sxs-lookup"><span data-stu-id="8a851-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="8a851-104">In .NET Framework 4.7 e versioni precedenti l'algoritmo di firma del messaggio predefinito è SHA1.</span><span class="sxs-lookup"><span data-stu-id="8a851-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8a851-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8a851-105">Suggestion</span></span>

<span data-ttu-id="8a851-106">Se si riscontrano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:</span><span class="sxs-lookup"><span data-stu-id="8a851-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="8a851-107">Nome</span><span class="sxs-lookup"><span data-stu-id="8a851-107">Name</span></span>    | <span data-ttu-id="8a851-108">Valore</span><span class="sxs-lookup"><span data-stu-id="8a851-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8a851-109">Scope</span><span class="sxs-lookup"><span data-stu-id="8a851-109">Scope</span></span>   |<span data-ttu-id="8a851-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="8a851-110">Minor</span></span>|
|<span data-ttu-id="8a851-111">Version</span><span class="sxs-lookup"><span data-stu-id="8a851-111">Version</span></span>|<span data-ttu-id="8a851-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="8a851-112">4.7.1</span></span>|
|<span data-ttu-id="8a851-113">Type</span><span class="sxs-lookup"><span data-stu-id="8a851-113">Type</span></span>|<span data-ttu-id="8a851-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="8a851-114">Runtime</span></span>|
