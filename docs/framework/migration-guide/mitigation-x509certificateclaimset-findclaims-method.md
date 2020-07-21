---
title: 'Mitigazione: Metodo X509CertificateClaimSet.FindClaims'
description: Informazioni su come il Metodo X509CertificateClaimSet. FindClaims è stato modificato per le app destinate a .NET Framework 4.6.1.
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
ms.openlocfilehash: 304d8fb5adc27b33f2410faaaf8662e0ff9be66d
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475320"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="698d3-103">Mitigazione: Metodo X509CertificateClaimSet.FindClaims</span><span class="sxs-lookup"><span data-stu-id="698d3-103">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>

<span data-ttu-id="698d3-104">A partire dalle app destinate a .NET Framework 4.6.1, il <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> metodo tenterà di far corrispondere l' `claimType` argomento a tutte le voci DNS nel relativo campo San.</span><span class="sxs-lookup"><span data-stu-id="698d3-104">Starting with apps that target .NET Framework 4.6.1, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="698d3-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="698d3-105">Impact</span></span>  
 <span data-ttu-id="698d3-106">Questa modifica interessa solo le app destinate a versioni di .NET Framework a partire da .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="698d3-106">This change only affects apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>  
  
 <span data-ttu-id="698d3-107">Per le app destinate a versioni precedenti di .NET Framework, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> cerca di far corrispondere l'argomento `claimType` solo con l'ultima voce DNS.</span><span class="sxs-lookup"><span data-stu-id="698d3-107">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="698d3-108">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="698d3-108">Mitigation</span></span>  
 <span data-ttu-id="698d3-109">Se questa modifica è indesiderata, le app destinate alle versioni del .NET Framework che iniziano con il .NET Framework 4.6.1 possono rifiutare esplicitamente questa modifica aggiungendo l'impostazione di configurazione seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="698d3-109">If this change is undesirable, apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1 can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 <span data-ttu-id="698d3-110">Inoltre, le app destinate alle versioni precedenti del .NET Framework ma sono in esecuzione nel .NET Framework 4.6.1 e versioni successive possono acconsentire esplicitamente a questo comportamento aggiungendo l'impostazione di configurazione seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="698d3-110">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="698d3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="698d3-111">See also</span></span>

- [<span data-ttu-id="698d3-112">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="698d3-112">Application compatibility</span></span>](application-compatibility.md)
