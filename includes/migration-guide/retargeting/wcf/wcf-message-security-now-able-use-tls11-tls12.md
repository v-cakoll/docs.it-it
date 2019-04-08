---
ms.openlocfilehash: 3b7b50700541649a785fa9bbe3ecc56c2697fbfc
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760269"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="c5433-101">La sicurezza dei messaggi di WCF è ora in grado di usare TLS1.1 e TLS1.2</span><span class="sxs-lookup"><span data-stu-id="c5433-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c5433-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c5433-102">Details</span></span>|<span data-ttu-id="c5433-103">A partire da .NET Framework 4.7 i clienti possono configurare TLS1.1 o TLS1.2 nella sicurezza dei messaggi di WCF oltre a SSL3.0 e TLS1.0 usando le impostazioni di configurazione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c5433-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="c5433-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c5433-104">Suggestion</span></span>|<span data-ttu-id="c5433-105">In .NET Framework 4.7 il supporto per TLS1.1 e TLS1.2 nella sicurezza dei messaggi di WCF è disattivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c5433-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="c5433-106">Per attivarlo, aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="c5433-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="c5433-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="c5433-107">Scope</span></span>|<span data-ttu-id="c5433-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c5433-108">Edge</span></span>|
|<span data-ttu-id="c5433-109">Versione</span><span class="sxs-lookup"><span data-stu-id="c5433-109">Version</span></span>|<span data-ttu-id="c5433-110">4.7</span><span class="sxs-lookup"><span data-stu-id="c5433-110">4.7</span></span>|
|<span data-ttu-id="c5433-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="c5433-111">Type</span></span>|<span data-ttu-id="c5433-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="c5433-112">Retargeting</span></span>|

