---
title: <transport> di <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 3126618eca6e8317968c6eb568a04615ec8de884
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073453"
---
# <a name="transport-of-msmqintegrationbinding"></a>\<Transport > di \<msmqIntegrationBinding >
Definisce le impostazioni di sicurezza per il trasporto di integrazione di Accodamento messaggi.  
  
 \<system.ServiceModel>  
\<le associazioni >  
msmqIntegrationBinding  
\<binding>  
\<security>  
\<transport>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Specifica come deve essere autenticato il messaggio dal trasporto MSMQ. Se viene impostato su `None`, anche il valore dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.<br /><br /> Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessuna autenticazione.<br />-   WindowsDomain: Il meccanismo di autenticazione Usa Active Directory per ottenere il certificato X.509 per il SID associato al messaggio. Questo viene quindi usato per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere nella coda.<br />-Certificato: Il canale Ottiene il certificato dall'archivio certificati.<br /><br /> Il valore predefinito è WindowsDomain. L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi. Di seguito vengono elencati i valori validi:<br /><br /> -RC4Stream<br />-   AES<br /><br /> Il valore predefinito è RC4Stream. L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Specifica come viene protetto il messaggio a livello del trasporto MSMQ. La crittografia assicura l'integrità del messaggio mentre EncryptAndSign assicura sia l'integrità che il non ripudio del messaggio; ovvero, il messaggio proviene effettivamente dal mittente e il mittente è quello che dichiara di essere.<br /><br /> -I valori validi includono quanto segue:<br />-None: Nessuna protezione.<br />-Accesso: I messaggi vengono firmati.<br />-   EncryptAndSign: I messaggi vengono crittografati e firmati.<br /><br /> Il valore predefinito è Sign. L'attributo è di tipo ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|-Specifica l'algoritmo da utilizzare nel calcolo del digest come parte delle firme. Di seguito vengono elencati i valori validi:<br />-   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Il valore predefinito è SHA1. L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>A causa di problemi di conflitto di MD5 e SHA1, Microsoft consiglia SHA256 o versione successiva.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Definisce le impostazioni di sicurezza per un'associazione MSMQ.|  
  
## <a name="remarks"></a>Note  
 Questo elemento incapsula le impostazioni di sicurezza per il trasporto di integrazione del servizio di accodamento di messaggi. Le impostazioni sono le stesse per l'integrazione di accodamento messaggi e trasporti in coda. Consente di impostare la modalità di autenticazione, l'algoritmo di crittografia, l'algoritmo hash protetto e il livello di protezione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
