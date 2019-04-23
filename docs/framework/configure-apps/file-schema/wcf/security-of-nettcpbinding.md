---
title: <security> di <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: 3fd850862172ad2b9bd58cd01d332028ff76462a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199076"
---
# <a name="security-of-nettcpbinding"></a>\<sicurezza > di \<netTcpBinding >
Definisce le impostazioni di sicurezza per un'associazione.  
  
 \<system.ServiceModel>  
\<le associazioni >  
\<netTcpBinding>  
\<binding>  
\<security>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|modalità|Facoltativo. Specifica il tipo di sicurezza applicata. I valori validi sono riportati di seguito. Il valore predefinito è `Transport`.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Attributo mode  
  
|Value|Descrizione|  
|-----------|-----------------|  
|nessuno|La sicurezza è disabilitata.|  
|Trasporto|La sicurezza del trasporto è fornita usando TLS su TCP o SPNego. Può essere necessario che il servizio sia configurato con certificati SSL. Con questa modalità è possibile controllare il livello di protezione.|  
|Messaggio|La sicurezza è fornita mediante la sicurezza dei messaggi SOAP. Per impostazione predefinita, il corpo SOAP viene crittografato e firmato. Questa modalità offre varie funzionalità, ad esempio se le credenziali del servizio sono disponibili per client fuori banda, il gruppo di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio. L'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.|  
|TransportWithMessageCredential|La sicurezza del trasporto è abbinata alla sicurezza del messaggio. La sicurezza del trasporto è fornita da TLS su TCP o SPNego e assicura integrità, riservatezza e autenticazione server. La sicurezza del messaggio SOAP fornisce l'autenticazione del client. Per impostazione predefinita, l'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)|Definisce le impostazioni di sicurezza per il trasporto. L'elemento è di tipo <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.|  
|[\<messaggio >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)|Definisce le impostazioni di sicurezza per il messaggio. L'elemento è di tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|binding|L'elemento di associazione del [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).|  
  
## <a name="remarks"></a>Note  
 Ognuna delle associazioni standard fornisce parametri per controllare i requisiti di sicurezza di trasferimento. Alcuni esempi tipici di elementi controllati da questi parametri sono la modalità di sicurezza che determina se la sicurezza è a livello di messaggio o a livello di trasporto e la scelta del tipo di credenziale client. L'infrastruttura crea uno stack di canali con il tipo di sicurezza appropriato a partire dal gruppo di opzioni impostate tramite questi parametri.  
  
 Le associazioni fornite da Windows Communication Foundation (WCF) formano un insieme progettato per soddisfare alcuni dei requisiti di scenario più comuni. Ognuna di queste associazioni consente la definizione mirata dei requisiti di sicurezza relativi ad alcuni scenari specifici.  
  
 Questo elemento di configurazione fornisce le specifiche di sicurezza per  `netTcpBinding`. Si tratta di un'associazione protetta, affidabile, ottimizzata e adatta per le comunicazioni fra computer. Tale associazione crea per impostazione predefinita uno stack di comunicazione in fase di esecuzione che, oltre a implementare la codifica binaria dei messaggi, usa il protocollo TCP per l'invio dei messaggi, Windows Security per proteggere e autenticare i messaggi e WS-ReliableMessaging per garantire l'affidabilità delle comunicazioni.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
