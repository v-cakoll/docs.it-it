---
ms.openlocfilehash: 0e949cbdeda99dd7b94e919b903a21171a57f527
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614489"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a><span data-ttu-id="f9ad5-101">Associazione WCF con la modalità di sicurezza TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="f9ad5-101">WCF binding with the TransportWithMessageCredential security mode</span></span>

#### <a name="details"></a><span data-ttu-id="f9ad5-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f9ad5-102">Details</span></span>

<span data-ttu-id="f9ad5-103">A partire da .NET Framework 4.6.1 l'associazione WCF che usa la modalità di sicurezza TransportWithMessageCredential può essere impostata in modo da ricevere i messaggi con intestazioni &quot;a&quot; non firmate per le chiavi di sicurezza asimmetriche. Per impostazione predefinita, le intestazioni &quot;a&quot; non firmate continueranno a essere rifiutate in .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-103">Beginning in the .NET Framework 4.6.1, WCF binding that uses the TransportWithMessageCredential security mode can be set up to receive messages with unsigned &quot;to&quot; headers for asymmetric security keys.By default, unsigned &quot;to&quot; headers will continue to be rejected in .NET Framework 4.6.1.</span></span> <span data-ttu-id="f9ad5-104">Verranno accettate solo se un'applicazione accetta in modo esplicito questa nuova modalità di funzionamento usando l'opzione di configurazione Switch.System.ServiceModel.AllowUnsignedToHeader.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-104">They will only be accepted if an application opts into this new mode of operation using the Switch.System.ServiceModel.AllowUnsignedToHeader configuration switch.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f9ad5-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f9ad5-105">Suggestion</span></span>

<span data-ttu-id="f9ad5-106">Poiché è una funzionalità che prevede il consenso esplicito, non dovrebbe influire sul comportamento delle app esistenti.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-106">Because this is an opt-in feature, it should not affect the behavior of existing apps.</span></span><br/><span data-ttu-id="f9ad5-107">Per stabilire se il nuovo comportamento deve essere usato o meno, usare l'impostazione di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="f9ad5-107">To control whether the new behavior is used or not, use the following configuration setting:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />
</runtime>
```

| <span data-ttu-id="f9ad5-108">Nome</span><span class="sxs-lookup"><span data-stu-id="f9ad5-108">Name</span></span>    | <span data-ttu-id="f9ad5-109">Valore</span><span class="sxs-lookup"><span data-stu-id="f9ad5-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f9ad5-110">Scope</span><span class="sxs-lookup"><span data-stu-id="f9ad5-110">Scope</span></span>   | <span data-ttu-id="f9ad5-111">Modalità trasparente</span><span class="sxs-lookup"><span data-stu-id="f9ad5-111">Transparent</span></span> |
| <span data-ttu-id="f9ad5-112">Version</span><span class="sxs-lookup"><span data-stu-id="f9ad5-112">Version</span></span> | <span data-ttu-id="f9ad5-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="f9ad5-113">4.6.1</span></span>       |
| <span data-ttu-id="f9ad5-114">Type</span><span class="sxs-lookup"><span data-stu-id="f9ad5-114">Type</span></span>    | <span data-ttu-id="f9ad5-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="f9ad5-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f9ad5-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="f9ad5-116">Affected APIs</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
