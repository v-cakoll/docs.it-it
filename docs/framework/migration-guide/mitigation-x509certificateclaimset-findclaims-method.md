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
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Mitigazione: Metodo X509CertificateClaimSet.FindClaims

A partire dalle app destinate a .NET Framework 4.6.1, il <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> metodo tenterà di abbinare l'argomento `claimType` a tutte le voci DNS nel relativo campo SAN.  
  
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
