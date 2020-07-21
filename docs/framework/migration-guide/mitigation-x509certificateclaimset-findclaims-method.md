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
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Mitigazione: Metodo X509CertificateClaimSet.FindClaims

A partire dalle app destinate a .NET Framework 4.6.1, il <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> metodo tenterà di far corrispondere l' `claimType` argomento a tutte le voci DNS nel relativo campo San.  
  
## <a name="impact"></a>Impatto  
 Questa modifica interessa solo le app destinate a versioni di .NET Framework a partire da .NET Framework 4.6.1.  
  
 Per le app destinate a versioni precedenti di .NET Framework, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> cerca di far corrispondere l'argomento `claimType` solo con l'ultima voce DNS.  
  
## <a name="mitigation"></a>Strategia di riduzione del rischio  
 Se questa modifica è indesiderata, le app destinate alle versioni del .NET Framework che iniziano con il .NET Framework 4.6.1 possono rifiutare esplicitamente questa modifica aggiungendo l'impostazione di configurazione seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'app:  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 Inoltre, le app destinate alle versioni precedenti del .NET Framework ma sono in esecuzione nel .NET Framework 4.6.1 e versioni successive possono acconsentire esplicitamente a questo comportamento aggiungendo l'impostazione di configurazione seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'app:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
