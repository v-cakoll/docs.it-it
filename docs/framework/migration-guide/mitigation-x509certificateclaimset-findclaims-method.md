---
title: 'Mitigazione: Metodo X509CertificateClaimSet.FindClaims'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
ms.openlocfilehash: f94a5f685a5aa94332bf2e15e5d5eb0def02d7ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79400141"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Mitigazione: Metodo X509CertificateClaimSet.FindClaims
A partire dalle app destinate a .NET Framework 4.6.1, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> tenterà di far corrispondere l'argomento `claimType` con tutte le voci DNS nel relativo campo SAN.  
  
## <a name="impact"></a>Impatto  
 Questa modifica interessa solo le app destinate a versioni di .NET Framework a partire da .NET Framework 4.6.1.  
  
 Per le app destinate a versioni precedenti di .NET Framework, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> cerca di far corrispondere l'argomento `claimType` solo con l'ultima voce DNS.  
  
## <a name="mitigation"></a>Strategia di riduzione del rischio  
 Se questa modifica è indesiderabile, le app destinate alle versioni di .NET Framework a partire da .NET Framework 4.6.1 possono rifiutarne esplicitamente aggiungendo la seguente impostazione di configurazione alla sezione>di [ \<runtime](../configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 Inoltre, le app destinate a versioni precedenti di .NET Framework ma in esecuzione in .NET Framework 4.6.1 [ \<](../configure-apps/file-schema/runtime/runtime-element.md) e versioni successive possono acconsentire esplicitamente a questo comportamento aggiungendo l'impostazione di configurazione seguente alla sezione>runtime del file di configurazione dell'app:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
