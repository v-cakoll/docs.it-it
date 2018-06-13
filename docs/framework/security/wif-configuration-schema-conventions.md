---
title: Convenzioni dello schema di configurazione di WIF
ms.date: 03/30/2017
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 3109b75ccf9cefcad4e112cca02e932ea5489d24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410403"
---
# <a name="wif-configuration-schema-conventions"></a>Convenzioni dello schema di configurazione di WIF
Questo argomento illustra le convenzioni usate negli argomenti relativi alla configurazione di Windows Identity Foundation (WIF) e descrive alcuni attributi e funzionalità comuni usati nelle sezioni [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) e [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).  
  
<a name="BKMK_Modes"></a>   
## <a name="modes"></a>Modalità  
 Molti elementi di configurazione WIF hanno un attributo `mode`. Questo attributo controlla in genere la classe usata per eseguire una determinata parte dell'elaborazione e gli elementi di configurazione consentiti come elementi figlio dell'elemento corrente. Viene generato un errore di configurazione se gli elementi inclusi nel file di configurazione vengono ignorati a causa delle impostazioni della modalità.  
  
<a name="BKMK_TimespanValues"></a>   
## <a name="timespan-values"></a>Valori TimeSpan  
 Quando <xref:System.TimeSpan> viene usato come tipo di attributo, vedere il metodo <xref:System.TimeSpan.Parse%28System.String%29> per conoscere il formato consentito. Il formato è conforme alle specifiche seguenti.  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 Ad esempio, "30", "30.00:00", "30.00:00:00" indicano tutti 30 giorni e "00:05", "00:05:00", "0.00:05:00.00" indicano tutti 5 minuti.  
  
<a name="BKMK_CertificateReferences"></a>   
## <a name="certificate-references"></a>Riferimenti ai certificati  
 Diversi elementi accettano riferimenti ai certificati tramite l'elemento `<certificateReference>`. Quando si fa riferimento a un certificato, sono disponibili gli attributi seguenti.  
  
|||  
|-|-|  
|`storeLocation`|Un valore dell'enumerazione <xref:System.Security.Cryptography.X509Certificates.StoreLocation>: `CurrentUser` o `CurrentMachine`.|  
|`storeName`|Un valore dell'enumerazione <xref:System.Security.Cryptography.X509Certificates.StoreName>. I valori più utili in questo contesto sono `My` e `TrustedPeople`.|  
|`x509FindType`|Un valore dell'enumerazione <xref:System.Security.Cryptography.X509Certificates.X509FindType>. I valori più utili in questo contesto sono `FindBySubjectName` e `FindByThumbprint`. Per eliminare le probabilità di errore, è consigliabile usare il tipo `FindByThumbprint` in ambienti di produzione.|  
|`findValue`|Il valore usato per trovare il certificato, basato sull'attributo `x509FindType`. Per eliminare le probabilità di errore, è consigliabile usare il tipo `FindByThumbprint` in ambienti di produzione. Quando si specifica `FindByThumbPrint`, questo attributo accetta un valore che è la forma di stringa esadecimale dell'identificazione personale del certificato, ad esempio "97249e1a5fa6bee5e515b82111ef524a4c91583f".|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## <a name="custom-type-references"></a>Riferimenti ai tipi personalizzati  
 Diversi elementi fanno riferimento ai tipi personalizzati usando l'attributo `type`. Questo attributo deve specificare il nome del tipo personalizzato. Per fare riferimento a un tipo dalla Global Assembly Cache (GAC), è necessario usare un nome sicuro. Per fare riferimento a un tipo da un assembly nella directory Bin/, è possibile usare un semplice riferimento qualificato dall'assembly. È possibile fare riferimento anche ai tipi definiti nella directory App_Code/ specificando semplicemente il nome del tipo senza qualifica tramite assembly.  
  
 I tipi personalizzati devono essere derivati dal tipo specificato e devono fornire un costruttore `public` predefinito (argomento 0).  
  
## <a name="see-also"></a>Vedere anche  
 [\<System. IdentityModel >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)  
 [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)
