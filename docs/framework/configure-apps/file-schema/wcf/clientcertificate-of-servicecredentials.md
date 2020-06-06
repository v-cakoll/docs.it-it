---
title: <clientCertificate> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: a8a78bbfcd9dfbf6975503a845d5bb4e2d24b13d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398130"
---
# <a name="clientcertificate-of-servicecredentials"></a>\<clientCertificate> di \<serviceCredentials>
Definisce un certificato X.509 usato per firmare e crittografare i messaggi da un client a un servizio in un modello di comunicazione duplex.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|Specifica le opzioni di autenticazione del certificato client.|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|Specifica il certificato da usare.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|Specifica le credenziali da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.|  
  
## <a name="remarks"></a>Commenti  
 Questo elemento viene usato quando il servizio deve disporre in anticipo del certificato del client per poter comunicare in modo sicuro con il client. Questa esigenza si presenta quando si usa il modello di comunicazione duplex. Nel modello più comune di comunicazione richiesta/risposta, il client include il proprio certificato nella richiesta e il servizio usa tale certificato per crittografare e firmare la risposta che invia al client. Nel modello di comunicazione duplex, tuttavia, il servizio non riceve alcuna richiesta dal client e pertanto deve disporre in anticipo del certificato del client per proteggere il messaggio da inviare al client. Questo certificato deve quindi essere ottenuto mediante una negoziazione fuori banda e deve essere specificato tramite questo elemento. Per ulteriori informazioni sui servizi duplex, vedere [procedura: creare un contratto duplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
 Il certificato impostato in questo elemento viene usato per crittografare i messaggi indirizzati al client solo per le associazioni configurate con la modalità di autenticazione di sicurezza dei messaggi `MutualCertificateDuplex`.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [Procedura: creare un contratto duplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)
