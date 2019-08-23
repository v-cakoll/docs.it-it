---
title: <certificate> di <peer>
ms.date: 03/30/2017
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
ms.openlocfilehash: 72128aca1321f3adc4c99ce0e3a47489b1640e31
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919595"
---
# <a name="certificate-of-peer"></a>\<> certificato di \<> peer
Specifica un certificato usato da un peer.  
  
 \<system.ServiceModel>  
\<comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
\<serviceCredentials>  
\<> peer  
\<> certificato  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<certificate findValue = "String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|`findValue`|Stringa che contiene il valore da cercare nell'archivio certificati X.509. Il tipo contenuto nell'attributo deve soddisfare i requisiti del valore `x509FindType` specificato. Il valore predefinito è una stringa vuota.|  
|`storeLocation`|Specifica il percorso dell'archivio certificati X.509 usato dal client per eseguire la convalida del certificato peer. Di seguito vengono elencati i valori validi:<br /><br /> -LocalMachine: l'archivio certificati assegnato al computer locale.<br />-CurrentUser: l'archivio certificati assegnato all'utente corrente.<br /><br /> L'impostazione predefinita è LocalMachine.|  
|`storeName`|Specifica il nome dell'archivio certificati X.509 da aprire. Di seguito vengono elencati i valori validi:<br /><br /> AddressBook Archivio certificati per altri utenti.<br />AuthRoot Archivio certificati per autorità di certificazione (CA) di terze parti.<br />CertificateAuthority Archivio certificati per autorità di certificazione intermedie (CAs).<br />Consentiti Archivio certificati per i certificati revocati.<br />My Archivio certificati per i certificati personali.<br />Radice Archivio certificati per autorità di certificazione radice attendibili (CAs).<br />TrustedPeople Archivio certificati per utenti e risorse direttamente attendibili.<br />TrustedPublisher Archivio certificati per autori direttamente attendibili.<br /><br /> L'impostazione predefinita è My.|  
|`X509FindType`|Definisce il tipo di ricerca X.509 da eseguire. Di seguito vengono elencati i valori validi:<br /><br /> -   FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />- FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore `X509FindType` specificato.<br /><br /> L'impostazione predefinita è FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|Specifica le credenziali correnti per un nodo peer.|  
  
## <a name="remarks"></a>Note  
 Questa elemento di configurazione contiene un'istanza `X509Certificate2` usata per autenticare elementi adiacenti nella rete di peer.  
  
 Per ulteriori informazioni sulla programmazione peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [Uso di certificati](../../../wcf/feature-details/working-with-certificates.md)
- [Reti peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Autenticazione del messaggio Peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Peer Channel autenticazione personalizzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Protezione di applicazioni del canale peer](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
