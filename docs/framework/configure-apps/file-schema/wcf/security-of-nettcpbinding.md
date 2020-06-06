---
title: <security> di <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: aa01e906ddd2f15007c72bfc2a45122cfb15ba2c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736366"
---
# <a name="security-of-nettcpbinding"></a>\<security> di \<netTcpBinding>
Definisce le impostazioni di sicurezza per un'associazione.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
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
|mode|Facoltativa. Specifica il tipo di sicurezza applicata. I valori validi sono riportati di seguito. Il valore predefinito è `Transport`.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Attributo mode  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|nessuno|La sicurezza è disabilitata.|  
|Trasporto|La sicurezza del trasporto è fornita usando TLS su TCP o SPNego. Può essere necessario che il servizio sia configurato con certificati SSL. È possibile controllare il livello di protezione con questa modalità.|  
|Message|La sicurezza è fornita mediante la sicurezza dei messaggi SOAP. Per impostazione predefinita, il corpo SOAP viene crittografato e firmato. Questa modalità offre varie funzionalità, ad esempio se le credenziali del servizio sono disponibili per client fuori banda, il gruppo di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio. L'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.|  
|TransportWithMessageCredential|La sicurezza del trasporto è abbinata alla sicurezza del messaggio. La sicurezza del trasporto è fornita da TLS su TCP o SPNego e assicura integrità, riservatezza e autenticazione server. La sicurezza del messaggio SOAP fornisce l'autenticazione del client. Per impostazione predefinita, l'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|Definisce le impostazioni di sicurezza per il trasporto. L'elemento è di tipo <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.|  
|[\<message>](message-element-of-nettcpbinding.md)|Definisce le impostazioni di sicurezza per il messaggio. L'elemento è di tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|binding|Elemento di associazione di [\<netTcpBinding>](nettcpbinding.md) .|  
  
## <a name="remarks"></a>Commenti  
 Ognuna delle associazioni standard fornisce parametri per controllare i requisiti di sicurezza di trasferimento. Alcuni esempi tipici di elementi controllati da questi parametri sono la modalità di sicurezza che determina se la sicurezza è a livello di messaggio o a livello di trasporto e la scelta del tipo di credenziale client. L'infrastruttura crea uno stack di canali con il tipo di sicurezza appropriato a partire dal gruppo di opzioni impostate tramite questi parametri.  
  
 Le associazioni fornite da Windows Communication Foundation (WCF) formano un insieme progettato per soddisfare alcuni dei requisiti di scenario più comuni. Ognuna di queste associazioni consente la definizione mirata dei requisiti di sicurezza relativi ad alcuni scenari specifici.  
  
 Questo elemento di configurazione fornisce le specifiche di sicurezza per  `netTcpBinding`. Si tratta di un'associazione protetta, affidabile, ottimizzata e adatta per le comunicazioni fra computer. Tale associazione crea per impostazione predefinita uno stack di comunicazione in fase di esecuzione che, oltre a implementare la codifica binaria dei messaggi, usa il protocollo TCP per l'invio dei messaggi, Windows Security per proteggere e autenticare i messaggi e WS-ReliableMessaging per garantire l'affidabilità delle comunicazioni.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Binding](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
