---
title: Programmazione delle funzionalità di sicurezza di WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message security [WCF], programming overview
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
ms.openlocfilehash: 2b3c96e91c0d6f01fa30b3b617449e7d4a148933
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596773"
---
# <a name="programming-wcf-security"></a>Programmazione delle funzionalità di sicurezza di WCF
In questo argomento vengono descritte le attività di programmazione fondamentali utilizzate per creare un'applicazione Secure Windows Communication Foundation (WCF). Questo argomento descrive solo l'autenticazione, la riservatezza e l'integrità, collettivamente nota come *protezione del trasferimento*. In questo argomento non viene illustrata l'autorizzazione (controllo dell'accesso a risorse o servizi); per informazioni sull'autorizzazione, vedere [autorizzazione](authorization-in-wcf.md).  
  
> [!NOTE]
> Per un'introduzione importante ai concetti relativi alla sicurezza, in particolare per quanto riguarda WCF, vedere le esercitazioni sui modelli e sulle procedure in MSDN in [scenari, modelli e indicazioni sull'implementazione di WSE (Web Services Enhancements) 3,0](https://docs.microsoft.com/previous-versions/msp-n-p/ff648183(v=pandp.10)).  
  
 La programmazione della sicurezza WCF si basa su tre passaggi che configurano quanto segue: la modalità di sicurezza, un tipo di credenziale client e i valori delle credenziali. Questi passaggi possono essere eseguiti in codice o in configurazione.  
  
## <a name="setting-the-security-mode"></a>Impostazione della modalità di sicurezza  
 Di seguito vengono illustrati i passaggi generali per la programmazione con la modalità di sicurezza in WCF:  
  
1. Scegliere fra le associazioni predefinite un'associazione appropriata ai requisiti dell'applicazione. Per un elenco delle opzioni di associazione, vedere [associazioni fornite dal sistema](../system-provided-bindings.md). Per impostazione predefinita, quasi tutte le associazioni presentano un meccanismo di sicurezza abilitato. L'unica eccezione è la <xref:System.ServiceModel.BasicHttpBinding> classe (mediante la configurazione, [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) ).  
  
     L'associazione scelta determina il trasporto. Ad esempio, l'associazione <xref:System.ServiceModel.WSHttpBinding> utilizza il protocollo HTTP come trasporto, mentre l'associazione <xref:System.ServiceModel.NetTcpBinding> utilizza il trasporto TCP.  
  
2. Selezionare per l'associazione una delle modalità di sicurezza. Si noti che l'insieme delle modalità fra cui è possibile scegliere dipende dall'associazione scelta. Ad esempio, l'associazione <xref:System.ServiceModel.WSDualHttpBinding> non consente di scegliere la sicurezza a livello di trasporto. Analogamente, né l'associazione <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> né l'associazione <xref:System.ServiceModel.NetNamedPipeBinding> consentono di scegliere la sicurezza a livello di messaggio.  
  
     Sono disponibili tre opzioni:  
  
    1. `Transport`  
  
         La sicurezza a livello di trasporto dipende dal meccanismo utilizzato dall'associazione scelta. Ad esempio, se si utilizza l'associazione `WSHttpBinding`, il meccanismo di sicurezza è Secure Sockets Layer (SSL), che peraltro è anche il meccanismo del protocollo HTTPS. In generale, il vantaggio principale della sicurezza a livello di trasporto è che offre una buona velocità effettiva indipendentemente dal trasporto utilizzato. Tuttavia, tale tipo di sicurezza presenta due limiti. Anzitutto, il meccanismo di trasporto impone il tipo di credenziale utilizzato per autenticare un utente. Di fatto ciò rappresenta uno svantaggio solo se un servizio deve garantire l'interoperabilità con altri servizi che richiedono vari tipi di credenziali. Inoltre, poiché la sicurezza non viene applicata a livello di messaggio, la sicurezza viene implementata in modo hop-by-hop anziché end-to-end. Questo secondo limite rappresenta un problema solo se il percorso dei messaggi fra client e servizio prevede intermediari. Per ulteriori informazioni sul trasporto da utilizzare, vedere [scelta di un trasporto](choosing-a-transport.md). Per altre informazioni sull'uso della sicurezza del trasporto, vedere [Panoramica della sicurezza del trasporto](transport-security-overview.md).  
  
    2. `Message`  
  
         Nella sicurezza a livello di messaggio, ogni messaggio contiene le intestazioni e i dati necessari a garantire la sicurezza del messaggio. Poiché la composizione delle intestazioni è variabile, è possibile includere qualsiasi numero di credenziali. Ciò risulta essere un fattore rilevante se occorre interoperare con altri servizi che richiedono un tipo di credenziale specifico che un meccanismo di trasporto non è in grado di fornire, oppure se il messaggio deve essere utilizzato in più servizi, ognuno avente un requisito specifico di tipo di credenziale.  
  
         Per ulteriori informazioni, vedere [sicurezza dei messaggi](message-security-in-wcf.md).  
  
    3. `TransportWithMessageCredential`  
  
         Questa scelta utilizza il livello di trasporto per proteggere il trasferimento dei messaggi, ognuno dei quali contiene le credenziali dettagliate richieste dagli altri servizi. Ciò combina il vantaggio in termini di prestazioni della sicurezza a livello di trasporto con il vantaggio delle credenziali dettagliate della sicurezza a livello di messaggio. Questa opzione è disponibile per le associazioni seguenti: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> e <xref:System.ServiceModel.WSHttpBinding>.  
  
3. Se si decide di utilizzare la sicurezza a livello di trasporto per il protocollo HTTP (ovvero il protocollo HTTPS), è inoltre necessario configurare l'host con un certificato SSL e quindi abilitare il protocollo SSL su una porta. Per ulteriori informazioni, vedere la pagina relativa alla [sicurezza del trasporto http](http-transport-security.md).  
  
4. Se si utilizza l'associazione <xref:System.ServiceModel.WSHttpBinding> e non occorre stabilire una sessione protetta, impostare la proprietà <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> su `false`.  
  
     Una sessione protetta si verifica quando un client e un servizio creano un canale utilizzando una chiave simmetrica, ovvero quando sia il client sia il server utilizzano la stessa chiave per la durata della conversazione e fino alla chiusura del dialogo.  
  
## <a name="setting-the-client-credential-type"></a>Impostazione del tipo di credenziale client  
 Selezionare un tipo di credenziale client in base alle proprie esigenze. Per ulteriori informazioni, vedere [selezione di un tipo di credenziale](selecting-a-credential-type.md). Sono disponibili i tipi di credenziale client seguenti:  
  
- `Windows`  
  
- `Certificate`  
  
- `Digest`  
  
- `Basic`  
  
- `UserName`  
  
- `NTLM`  
  
- `IssuedToken`  
  
 L'impostazione del tipo di credenziale dipende dalla modalità impostata. Se ad esempio è stata selezionata l'associazione `wsHttpBinding` e la modalità è stata impostata sulla sicurezza a livello di messaggio, l'attributo `clientCredentialType` dell'elemento Message può essere impostato su uno dei valori seguenti: `None`, `Windows`, `UserName`, `Certificate` e `IssuedToken`, come mostrato nell'esempio di configurazione seguente.  
  
```xml  
<system.serviceModel>  
<bindings>  
  <wsHttpBinding>  
    <binding name="myBinding">  
      <security mode="Message"/>  
      <message clientCredentialType="Windows"/>  
    </binding>
  </wsHttpBinding>
</bindings>  
</system.serviceModel>  
```  
  
 Oppure nel codice:  
  
 [!code-csharp[c_WsHttpService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#1)]
 [!code-vb[c_WsHttpService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#1)]  
  
## <a name="setting-service-credential-values"></a>Impostazione dei valori di credenziale del servizio  
 Dopo aver selezionato un tipo di credenziale client è necessario impostare le credenziali effettivamente utilizzate dal servizio e dal client. Nel servizio, le credenziali vengono impostate utilizzando la classe <xref:System.ServiceModel.Description.ServiceCredentials> e restituite tramite la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> della classe <xref:System.ServiceModel.ServiceHostBase>. L'associazione utilizzata determina il tipo di credenziale del servizio, la scelta della modalità di sicurezza e il tipo di credenziale client. Nel codice seguente un certificato viene impostato come credenziale di servizio.  
  
 [!code-csharp[c_tcpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#3)]
 [!code-vb[c_tcpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#3)]  
  
## <a name="setting-client-credential-values"></a>Impostazione dei valori di credenziale del client  
 Nel client, i valori di credenziale vengono impostati utilizzando la classe <xref:System.ServiceModel.Description.ClientCredentials> e restituiti tramite la proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601>. Nel codice seguente un certificato viene impostato come credenziale in un client che utilizza il protocollo TCP.  
  
 [!code-csharp[c_TcpClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpclient/cs/source.cs#1)]
 [!code-vb[c_TcpClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpclient/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione WCF di base](../basic-wcf-programming.md)
- [Scenari di sicurezza comuni](common-security-scenarios.md)
