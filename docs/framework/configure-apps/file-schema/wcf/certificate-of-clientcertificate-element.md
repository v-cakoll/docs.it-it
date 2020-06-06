---
title: <certificate>dell' <clientCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: d0c4ef9d3657d2dfa787feb3576beda09d1997a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400538"
---
# <a name="certificate-of-clientcertificate-element"></a>\<certificate>dell' \<clientCertificate> elemento
Specifica un certificato X.509 usato per firmare e crittografare messaggi.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`findValue`|Stringa che contiene il valore da cercare nell'archivio certificati X.509. Il tipo contenuto in questo attributo deve soddisfare i requisiti del valore X509FindType specificato. Il valore predefinito è una stringa vuota.|  
|`storeLocation`|Specifica il percorso dell'archivio certificati X.509 usato dal client per convalidare il certificato sul server. I valori validi sono i seguenti:<br /><br /> -LocalMachine: l'archivio certificati assegnato al computer locale.<br />-CurrentUser: l'archivio certificati assegnato all'utente corrente.<br /><br /> Il valore predefinito è LocalMachine.|  
|`storeName`|Specifica il nome dell'archivio certificati X.509 da aprire. I valori validi sono i seguenti:<br /><br /> -AddressBook: archivio certificati per altri utenti.<br />-AuthRoot: archivio certificati per autorità di certificazione (CA) di terze parti.<br />-CertificationAuthority: archivio certificati per autorità di certificazione intermedie (CAs).<br />-Non consentito: archivio certificati per i certificati revocati.<br />-My: archivio certificati per i certificati personali.<br />-Root: archivio certificati per autorità di certificazione radice attendibili (CAs).<br />-TrustedPeople: archivio certificati per utenti e risorse direttamente attendibili.<br />-TrustedPublisher: archivio certificati per autori direttamente attendibili.<br /><br /> L'impostazione predefinita è My.|  
|`X509FindType`|Definisce il tipo di ricerca X.509 da eseguire. I valori validi sono i seguenti:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />- FindByTemplateName<br />- FindByApplicationPolicy<br />- FindByCertificatePolicy<br />- FindByExtension<br />- FindByKeyUsage<br />- FindBySubjectKeyIdentifier<br /><br /> Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore X509FindType specificato.<br /><br /> L'impostazione predefinita è FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento `<certificate>` viene usato quando il servizio deve disporre in anticipo del certificato del client per poter comunicare in modo sicuro con quest'ultimo. Questa esigenza si presenta quando si usa il modello di comunicazione duplex. Nel modello più comune di comunicazione richiesta/risposta, il client include il proprio certificato nella richiesta e il servizio usa tale certificato per crittografare e firmare la risposta che invia al client. Nel modello di comunicazione duplex, tuttavia, il servizio non riceve alcuna richiesta dal client e pertanto deve disporre in anticipo del certificato del client per proteggere il messaggio da inviare al client. Questo certificato deve quindi essere ottenuto mediante una negoziazione fuori banda e deve essere specificato tramite questo elemento. Per ulteriori informazioni sui servizi duplex, vedere [procedura: creare un contratto duplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene illustrato come individuare un certificato X.509 appropriato e un tipo di convalida personalizzato nell'elemento `<authentication>`.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Procedura: creare un servizio che usa un validator del certificato personalizzato](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)
