---
title: <authentication>dell' <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398222"
---
# <a name="authentication-of-servicecertificate-element"></a>\<authentication>dell' \<serviceCertificate> elemento
Specifica le impostazioni usate dal proxy del client per autenticare i certificati dei servizi ottenuti mediante la negoziazione SSL/TLS.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|customCertificateValidatorType|Stringa. Un tipo e un assembly usati per convalidare un tipo personalizzato.|  
|certificateValidationMode|Specifica una delle tre modalità usate per convalidare credenziali. Se è impostato su `Custom`, è necessario fornire anche un customCertificateValidator. Il valore predefinito è `ChainTrust`.|  
|revocationMode|Una delle modalità usate per verificare un elenco dei certificati revocati. Il valore predefinito è `Online`.|  
|trustedStoreLocation|Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`. Questo valore viene usato quando viene negoziato un certificato del servizio con il client. La convalida viene eseguita sull'archivio **persone attendibili** nel percorso di archiviazione specificato. Il valore predefinito è `CurrentUser`.|  
  
## <a name="customcertificatevalidator-attribute"></a>Attributo customCertificateValidator  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|string|Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.|  
  
## <a name="certificatevalidationmode-attribute"></a>Attributo certificateValidationMode  
  
|Valore|Description|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>Attributo revocationMode  
  
|Valore|Description|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: NoCheck, Online, Offline.<br /><br /> Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>Attributo trustedStoreLocation  
  
|Valore|Description|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: LocalMachine o CurrentUser. L'impostazione predefinita è CurrentUser. Se l'applicazione client è in esecuzione con un account di sistema, il certificato è in genere in LocalMachine. Se l'applicazione client è in esecuzione con un account utente, il certificato è in genere in CurrentUser.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|Specifica un certificato da usare per l'autenticazione di un servizio presso il client.|  
  
## <a name="remarks"></a>Commenti  
 L'attributo `certificateValidationMode` di questo elemento di configurazione specifica il livello di attendibilità usato per autenticare i certificati. Per impostazione predefinita, il livello è impostato su `ChainTrust`. Tale impostazione prevede che ogni certificato appartenga a una gerarchia di certificati che termina in un'autorità di certificazione attendibile situata all'inizio della catena. Si tratta della modalità più protetta. Il livello può inoltre essere impostato su `PeerOrChainTrust`, a indicare che sia i certificati autocertificati (trust peer) sia i certificati appartenenti a una catena di trust sono ritenuti attendibili. Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi. Quando si distribuisce un client è invece opportuno usare il livello `ChainTrust`. È inoltre possibile impostare il valore su `Custom` o `None`. Per usare il valore `Custom` è necessario impostare anche l'attributo `customCertificateValidator` sull'assembly e sul tipo usati per convalidare il certificato. Per creare una convalida personalizzata, è necessario ereditare una classe dalla classe X509CertificateValidator astratta. Per altre informazioni, vedere [procedura: creare un servizio che usa un validator del certificato personalizzato](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 L'attributo `revocationMode` specifica il modo in cui i certificati vengono contrassegnati per la revoca. L'impostazione predefinita è `online` a indicare che i certificati vengono contrassegnati automaticamente per la revoca. Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio vengono svolte due attività: Per prima cosa specifica un certificato di servizio che il client deve usare durante la comunicazione con gli endpoint il cui nome di dominio è `www.contoso.com` sul protocollo http. In secondo luogo, specifica la modalità di revoca e il percorso dell'archivio usati durante l'autenticazione.  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)
- [Procedura: creare un servizio che usa un validator del certificato personalizzato](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [Protezione di client](../../../wcf/securing-clients.md)
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
