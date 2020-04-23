---
title: 'Mitigazione: Metodo X509CertificateClaimSet.FindClaims'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
ms.openlocfilehash: 0b306960c4f11bb6f54aecaeb13297e7725e16a8
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102645"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="7d299-102">Mitigazione: Metodo X509CertificateClaimSet.FindClaims</span><span class="sxs-lookup"><span data-stu-id="7d299-102">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>

<span data-ttu-id="7d299-103">A partire dalle app destinate a .NET Framework 4.6.1, il <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> metodo tenterà di abbinare l'argomento `claimType` a tutte le voci DNS nel relativo campo SAN.</span><span class="sxs-lookup"><span data-stu-id="7d299-103">Starting with apps that target .NET Framework 4.6.1, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="7d299-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="7d299-104">Impact</span></span>  
 <span data-ttu-id="7d299-105">Questa modifica interessa solo le app destinate a versioni di .NET Framework a partire da .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="7d299-105">This change only affects apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>  
  
 <span data-ttu-id="7d299-106">Per le app destinate a versioni precedenti di .NET Framework, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> cerca di far corrispondere l'argomento `claimType` solo con l'ultima voce DNS.</span><span class="sxs-lookup"><span data-stu-id="7d299-106">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="7d299-107">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="7d299-107">Mitigation</span></span>  
 <span data-ttu-id="7d299-108">Se questa modifica è indesiderabile, le app destinate alle versioni di .NET Framework a partire da .NET Framework 4.6.1 possono rifiutarne esplicitamente aggiungendo la seguente impostazione di configurazione alla sezione>di [ \<runtime](../configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="7d299-108">If this change is undesirable, apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1 can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 <span data-ttu-id="7d299-109">Inoltre, le app destinate a versioni precedenti di .NET Framework ma in esecuzione in .NET Framework 4.6.1 [ \<](../configure-apps/file-schema/runtime/runtime-element.md) e versioni successive possono acconsentire esplicitamente a questo comportamento aggiungendo l'impostazione di configurazione seguente alla sezione>runtime del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="7d299-109">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d299-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d299-110">See also</span></span>

- [<span data-ttu-id="7d299-111">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="7d299-111">Application compatibility</span></span>](application-compatibility.md)
