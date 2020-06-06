---
title: <certificateReference> per <identity>
ms.date: 03/30/2017
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
ms.openlocfilehash: 93a6290d780ff61756f7315cd0c32f0e199ca00f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70849988"
---
# <a name="certificatereference-for-identity"></a>\<certificateReference> per \<identity>
Specifica le impostazioni per la convalida del certificato X.509. Un client Windows Communication Foundation protetto (WCF) che si connette a un endpoint con questa identità verifica che le attestazioni presentate dal server contengano l'attestazione di identità usata per costruire l'identità.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<certificateReference findValue="String"
                      isChainIncluded="Boolean"
                      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                      storeLocation="LocalMachine/CurrentUser"
                      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier">
</certificateReference>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|findValue|Specifica il valore da cercare nell'archivio certificati X.509. Il tipo contenuto in questo attributo deve soddisfare i requisiti del valore `X509FindType` specificato. Il valore predefinito è una stringa vuota.|  
|isChainIncluded|Valore booleano che specifica se la convalida viene eseguita usando una catena di certificati.|  
|storeLocation|Specifica il percorso dell'archivio certificati che il client può usare per convalidare il certificato del server.<br /><br /> I valori validi sono i seguenti:<br /><br /> -LocalMachine: archivio certificati assegnato al computer locale.<br />-CurrentUser: l'archivio certificati assegnato all'utente corrente.<br /><br /> Il valore predefinito è LocalMachine.<br /><br /> L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Specifica il nome dell'archivio certificati X.509 da aprire.<br /><br /> I valori validi sono i seguenti:<br /><br /> -AddressBook: archivio certificati per altri utenti.<br />-AuthRoot: archivio certificati per autorità di certificazione (CA) di terze parti.<br />-CertificateAuthority: archivio certificati per le autorità di certificazione intermedie.<br />-Non consentito: archivio certificati per i certificati revocati.<br />-My: archivio certificati per i certificati personali.<br />-Root: archivio certificati per CA radice attendibili.<br />-TrustedPeople: archivio certificati per utenti e risorse direttamente attendibili.<br />-TrustedPublisher: archivio certificati per autori direttamente attendibili.<br /><br /> Il valore predefinito è My.<br /><br /> L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Specifica il tipo di ricerca di certificati X.509 da eseguire. Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore X509FindType specificato.<br /><br /> I valori validi sono i seguenti:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />- FindByTemplateName<br />- FindByApplicationPolicy<br />- FindByCertificatePolicy<br />- FindByExtension<br />- FindByKeyUsage<br />- FindBySubjectKeyIdentifier<br /><br /> L'impostazione predefinita è FindBySubjectDistinguishedName.<br /><br /> L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Specifica le impostazioni che attivano l'autenticazione di un endpoint presso gli altri endpoint con cui scambia messaggi.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.CertificateReferenceElement>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
