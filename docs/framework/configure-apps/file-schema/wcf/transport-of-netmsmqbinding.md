---
title: <transport> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: ede4103f9c8f2f73ac34036fe7a58242e32350e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934684"
---
# <a name="transport-of-netmsmqbinding"></a>\<> di trasporto \<di NetMsmqBinding >
Definisce le impostazioni di sicurezza del trasporto.  
  
 \<system.ServiceModel>  
\<Binding >  
\<netMsmqBinding>  
\<binding>  
\<security>  
\<> di trasporto  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|msmqAuthenticationMode|Specifica come deve essere autenticato il messaggio dal trasporto MSMQ. Di seguito vengono elencati i valori validi:<br /><br /> Nessuno Nessuna autenticazione.<br />WindowsDomain Il meccanismo di autenticazione utilizza Active Directory per recuperare il certificato X. 509 per l'identificatore di sicurezza associato al messaggio. Questo viene quindi utilizzo per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere sulla coda.<br />Certificato Il canale Recupera il certificato dall'archivio certificati.<br /><br /> Il valore predefinito è `WindowsDomain`.<br /><br /> Se questo attributo viene impostato su `None`, anche l'attributo dell'attributo `msmqProtectionLevel` deve essere impostato su `None`. L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi. Di seguito vengono elencati i valori validi:<br /><br /> -RC4Stream<br />-   AES<br />-Il valore predefinito è `RC4Stream`. L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqProtectionLevel|Specifica il metodo di sicurezza dei messaggi al livello del trasporto MSMQ. La crittografia assicura l'integrità del messaggio, mentre la firma e la crittografa assicurano l'integrità del messaggio e il non ripudio. Ciò significa che il messaggio proviene effettivamente dal mittente e il mittente è quello indicato. Di seguito vengono elencati i valori validi:<br /><br /> Nessuno Nessuna protezione.<br />Sign I messaggi vengono firmati.<br />EncryptAndSign I messaggi vengono crittografati e firmati.<br />-Il valore predefinito `Sign`è.|  
|msmqSecureHashAlgorithm|Specifica l'algoritmo hash da usare per il calcolo del digest del messaggio. Di seguito vengono elencati i valori validi:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Il valore predefinito è `SHA1`. L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>A causa di problemi di collisione con MD5 e SHA1, Microsoft consiglia di SHA256 o meglio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|Definisce le impostazioni di sicurezza del trasporto per i trasporti in coda.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Code in WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
- [Associazioni](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
