---
title: '&lt;msmqTransportSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: f178ac3132e3c5880daef1d59480edae88f1d27e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180978"
---
# <a name="ltmsmqtransportsecuritygt"></a>&lt;msmqTransportSecurity&gt;
Specifica le impostazioni di sicurezza del trasporto MSMQ di un'associazione personalizzata.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<customBinding>  
\<binding>  
\<msmqIntegration >  
\<msmqTransportSecurity >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Specifica come deve essere autenticato il messaggio dal trasporto MSMQ. Se viene impostato su `None`, anche il valore dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.<br /><br /> Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessuna autenticazione.<br />-Windows: Il meccanismo di autenticazione Usa Active Directory per ottenere il certificato X.509 per il SID associato al messaggio. Questo viene quindi usato per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere nella coda.<br />-Certificate: Il canale Ottiene il certificato dall'archivio certificati.<br /><br /> L'impostazione predefinita è Windows. L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi. Di seguito vengono elencati i valori validi:<br /><br /> -RC4Stream<br />-   AES<br /><br /> Il valore predefinito è RC4Stream. L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Specifica come viene protetto il messaggio a livello del trasporto MSMQ. La crittografia assicura l'integrità del messaggio mentre EncryptAndSign assicura sia l'integrità che il non ripudio del messaggio; ovvero, il messaggio proviene effettivamente dal mittente e il mittente è quello che dichiara di essere. Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessuna protezione.<br />-Sign: I messaggi vengono firmati.<br />-EncryptAndSign: I messaggi vengono crittografati e firmati.<br /><br /> Il valore predefinito è Sign. L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Specifica l'algoritmo da usare nel calcolo del digest come parte delle firme. Di seguito vengono elencati i valori validi:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-SHA512<br /><br /> Il valore predefinito è SHA1. L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<msmqIntegration >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|Specifica le impostazioni necessarie per l'interazione con un mittente o un destinatario del sistema di accodamento messaggi (MSMQ).|  
|[\<msmqTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|Specifica le proprietà di comunicazione dell'accodamento per un servizio Windows Communication Foundation (WCF) che usa il protocollo MSMQ nativo.|  
  
## <a name="remarks"></a>Note  
 Per altre informazioni sulla protezione del trasporto, vedere [la sicurezza del trasporto](../../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Code in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Trasporti](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Scelta di un trasporto](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [Sicurezza del trasporto](../../../../../docs/framework/wcf/feature-details/transport-security.md)
