---
ms.openlocfilehash: 0a3dc43ebdc58d54675f2264a8ee56d9f4358cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859155"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="705a0-101">La sicurezza dei messaggi di WCF è ora in grado di usare TLS1.1 e TLS1.2</span><span class="sxs-lookup"><span data-stu-id="705a0-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="705a0-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="705a0-102">Details</span></span>|<span data-ttu-id="705a0-103">A partire da .NET Framework 4.7 i clienti possono configurare TLS1.1 o TLS1.2 nella sicurezza dei messaggi di WCF oltre a SSL3.0 e TLS1.0 usando le impostazioni di configurazione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="705a0-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="705a0-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="705a0-104">Suggestion</span></span>|<span data-ttu-id="705a0-105">In .NET Framework 4.7 il supporto per TLS1.1 e TLS1.2 nella sicurezza dei messaggi di WCF è disattivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="705a0-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="705a0-106">Per attivarlo, aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="705a0-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="705a0-107">Scope</span><span class="sxs-lookup"><span data-stu-id="705a0-107">Scope</span></span>|<span data-ttu-id="705a0-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="705a0-108">Edge</span></span>|
|<span data-ttu-id="705a0-109">Versione</span><span class="sxs-lookup"><span data-stu-id="705a0-109">Version</span></span>|<span data-ttu-id="705a0-110">4.7</span><span class="sxs-lookup"><span data-stu-id="705a0-110">4.7</span></span>|
|<span data-ttu-id="705a0-111">Type</span><span class="sxs-lookup"><span data-stu-id="705a0-111">Type</span></span>|<span data-ttu-id="705a0-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="705a0-112">Retargeting</span></span>|
