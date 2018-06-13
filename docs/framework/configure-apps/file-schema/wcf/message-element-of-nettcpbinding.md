---
title: Elemento &lt;message&gt; di &lt;netTcpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 1d71edd9-c085-4c2e-b6d3-980c313366f9
ms.openlocfilehash: 4a487d695cab259fc6b82fdf44b4c1bfdf5d04e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364126"
---
# <a name="ltmessagegt-element-of-ltnettcpbindinggt"></a>Elemento &lt;message&gt; di &lt;netTcpBinding&gt;
Definisce il tipo di requisiti di sicurezza a livello di messaggio per un endpoint configurato con il [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
 \<system.ServiceModel>  
\<le associazioni >  
\<netTcpBinding>  
\<binding>  
\<security>  
\<messaggio >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<message   
      algorithmSuite=System.Servicemodel.Security.SecurityAlgorithmsuite  
    clientCredentialType="None/Windows/UserName/Certificate/IssuedToken"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`algorithmSuite`|Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave. Gli algoritmi e le dimensioni della chiave sono determinati dalla classe <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Questi algoritmi sono associati a quelli specificati nelle specifiche del linguaggio dei criteri di sicurezza (WS-SecurityPolicy).<br /><br /> Nella tabella che segue sono riportati i valori possibili. Il valore predefinito è `Basic256`.<br /><br /> Se l'associazione del servizio specifica un valore `algorithmSuite` diverso dal valore predefinito e il file di configurazione viene generato usando Svcutil.exe, il file non verrà generato correttamente ed sarà necessario modificare manualmente il file di configurazione per impostare questo attributo sul valore desiderato.|  
|`clientCredentialType`|Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la sicurezza basata sul messaggio. Nella tabella che segue sono riportati i valori possibili. Il valore predefinito è `UserName`. L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.|  
  
## <a name="algorithmsuite-attribute"></a>Attributo algorithmSuite  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Basic128|Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic192|Usa crittografia Aes192, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic256|Usa crittografia Aes256, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic256Rsa15|Usa Aes256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|Basic192Rsa15|Usa Aes192 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|TripleDes|Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic128Rsa15|Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|TripleDesRsa15|Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|Basic128Sha256|Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic192Sha256|Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic256Sha256|Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|TripleDesSha256|Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.|  
|Basic128Sha256Rsa15|Usa Aes128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|Basic192Sha256Rsa15|Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|Basic256Sha256Rsa15|Usa Aes256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
|TripleDesSha256Rsa15|Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.|  
  
## <a name="clientcredentialtype-attribute"></a>Attributo clientCredentialType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|None|None: consente al servizio di interagire con i client anonimi. Sul servizio, indica che il servizio non richiede alcuna credenziale client. Sul client, indica che il client non fornisce alcuna credenziale client.|  
|Windows|consente lo svolgimento degli scambi SOAP nel contesto autenticato di una credenziale di Windows.|  
|UserName|Consente al servizio di richiedere che l'autenticazione del client sia eseguita tramite una credenziale UserName. WCF non supporta l'invio di un digest delle password, né la derivazione delle chiavi password e l'uso di tali chiavi per la sicurezza del messaggio. Di conseguenza, WCF richiede che il trasporto sia protetto quando si utilizza le credenziali UserName. Questa modalità di credenziale produce un scambio interoperabile o una negoziazione non interoperabile basata sull'attributo `negotiateServiceCredential`.|  
|Certificato|Consente al servizio di richiedere che l'autenticazione del client si basi su un certificato. Se viene usata la modalità di sicurezza del messaggio e l'attributo `negotiateServiceCredential` è impostato su `false`, sarà necessario eseguire il provisioning del client tramite il certificato del servizio.|  
|IssuedToken|Specifica un token personalizzato, emesso da un servizio di token di sicurezza.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Definisce le funzionalità di sicurezza dell'<xref:System.ServiceModel.Configuration.NetTcpBindingElement>.|  
  
## <a name="remarks"></a>Note  
 Il messaggio usa la sicurezza a livello di messaggio per garantire l'integrità e la riservatezza del messaggio SOAP e per svolgere l'autenticazione reciproca dei peer di comunicazione. Se questa modalità di sicurezza viene selezionata per un'associazione, nello stack di canali vengono configurati elementi di associazione di sicurezza dei messaggi e i messaggi SOAP vengono protetti in conformità agli standard WS-Security*.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.MessageSecurityOverTcp>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetTcpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare i client e servizi Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
