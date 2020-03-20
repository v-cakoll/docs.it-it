---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5899c609b3cf52c4a275ba6fb10c5826fcf37f1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153009"
---
# <a name="msmqtransportsecurity"></a>\<> msmqTransportSecurity
Specifica le impostazioni di sicurezza del trasporto MSMQ di un'associazione personalizzata.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<associazioni>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>customBinding**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di associazione**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity (>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Specifica come deve essere autenticato il messaggio dal trasporto MSMQ. Se viene impostato su `None`, anche il valore dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.<br /><br /> I valori validi sono i seguenti:<br /><br /> - Nessuno: nessuna autenticazione.- None: No authentication.<br />- Windows: il meccanismo di autenticazione utilizza Active Directory per ottenere il certificato X.509 per il SID associato al messaggio.- Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message. Questo viene quindi usato per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere nella coda.<br />- Certificato: il canale ottiene il certificato dall'archivio certificati.- Certificate: The channel gets the certificate from the certificate store.<br /><br /> L'impostazione predefinita è Windows. L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi. I valori validi sono i seguenti:<br /><br /> - RC4Stream<br />- AES<br /><br /> Il valore predefinito è RC4Stream. L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Specifica come viene protetto il messaggio a livello del trasporto MSMQ. La crittografia garantisce l'integrità dei messaggi mentre EncryptAndSign garantisce l'integrità dei messaggi e il non ripudio; cioè, il messaggio proviene effettivamente dal mittente e il mittente è chi dicono di essere. I valori validi sono i seguenti:<br /><br /> - Nessuno: nessuna protezione.<br />- Segno: i messaggi sono firmati.<br />- EncryptAndSign: i messaggi vengono crittografati e firmati.- EncryptAndSign: Messages are encrypted and signed.<br /><br /> Il valore predefinito è Sign. L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Specifica l'algoritmo da usare nel calcolo del digest come parte delle firme. I valori validi sono i seguenti:<br /><br /> - MD5 (in quadra sto )<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> Il valore predefinito è SHA1. L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>A causa di problemi di collisione con MD5 e SHA1, Microsoft consiglia SHA256 o versione migliore.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|Specifica le impostazioni necessarie per l'interazione con un mittente o un destinatario del sistema di accodamento messaggi (MSMQ).|  
|[\<>mqTransport](msmqtransport.md)|Specifica le proprietà di comunicazione dell'accodamento per un servizio Windows Communication Foundation (WCF) che usa il protocollo MSMQ nativo.|  
  
## <a name="remarks"></a>Osservazioni  
 Per ulteriori informazioni sulla sicurezza del trasporto, vedere [Protezione del trasporto](../../../wcf/feature-details/transport-security.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Code in WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Trasporti](../../../wcf/feature-details/transports.md)
- [Scelta di un trasporto](../../../wcf/feature-details/choosing-a-transport.md)
- [Associazioni](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<>customBinding](custombinding.md)
- [Sicurezza dei trasporti](../../../wcf/feature-details/transport-security.md)
