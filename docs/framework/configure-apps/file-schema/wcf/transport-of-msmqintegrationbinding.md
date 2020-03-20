---
title: <transport> di <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 1cb165fed9266307335482166116c4c1d62efe7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152957"
---
# <a name="transport-of-msmqintegrationbinding"></a>\<> di \<trasporto del> msmqIntegrationBindingTransport> of msmqIntegrationBinding>
Definisce le impostazioni di sicurezza per il trasporto di integrazione di Accodamento messaggi.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<associazioni>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>msmqIntegrationBinding**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di associazione**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di sicurezza**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>dei trasporti**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Specifica come deve essere autenticato il messaggio dal trasporto MSMQ. Se viene impostato su `None`, anche il valore dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.<br /><br /> I valori validi sono i seguenti:<br /><br /> - Nessuno: nessuna autenticazione.- None: No authentication.<br />- WindowsDomain: il meccanismo di autenticazione utilizza Active Directory per ottenere il certificato X.509 per il SID associato al messaggio. Questo viene quindi usato per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere nella coda.<br />- Certificato: il canale ottiene il certificato dall'archivio certificati.- Certificate: The channel gets the certificate from the certificate store.<br /><br /> Il valore predefinito è WindowsDomain. L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi. I valori validi sono i seguenti:<br /><br /> - RC4Stream<br />- AES<br /><br /> Il valore predefinito è RC4Stream. L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Specifica come viene protetto il messaggio a livello del trasporto MSMQ. La crittografia garantisce l'integrità dei messaggi mentre EncryptAndSign garantisce l'integrità dei messaggi e il non ripudio; cioè, il messaggio proviene effettivamente dal mittente e il mittente è chi dicono di essere.<br /><br /> - I valori validi sono i seguenti:<br />- Nessuno: nessuna protezione.<br />- Segno: i messaggi sono firmati.<br />- EncryptAndSign: i messaggi vengono crittografati e firmati.- EncryptAndSign: Messages are encrypted and signed.<br /><br /> Il valore predefinito è Sign. L'attributo è di tipo ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|- Specifica l'algoritmo da utilizzare nel calcolo del digest come parte delle firme. I valori validi sono i seguenti:<br />- MD5 (in quadra sto )<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> Il valore predefinito è SHA1. L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>A causa di problemi di collisione con MD5 e SHA1, Microsoft consiglia SHA256 o versione migliore.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>di sicurezza](security-of-basichttpbinding.md)|Definisce le impostazioni di sicurezza per un'associazione MSMQ.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo elemento incapsula le impostazioni di sicurezza per il trasporto di integrazione del servizio di accodamento di messaggi. Le impostazioni sono le stesse per l'integrazione di accodamento messaggi e trasporti in coda. Consente di impostare la modalità di autenticazione, l'algoritmo di crittografia, l'algoritmo hash protetto e il livello di protezione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Associazioni](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<>di associazione](bindings.md)
