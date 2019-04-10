---
title: Programmazione delle funzionalità di sicurezza di WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message security [WCF], programming overview
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
ms.openlocfilehash: d327605c084cd5fb1c65fbb786e871b421730b83
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313320"
---
# <a name="programming-wcf-security"></a>Programmazione delle funzionalità di sicurezza di WCF
Questo argomento descrive le attività di programmazione fondamentali utilizzate per creare un'applicazione Windows Communication Foundation (WCF) sicuro. Questo argomento descrive solo l'autenticazione, riservatezza e integrità, complessivamente note come *protezione del trasferimento*. In questo argomento non descrive l'autorizzazione (controllo di accesso a risorse o servizi); Per informazioni sull'autorizzazione, vedere [autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
> [!NOTE]
>  Per un'introduzione ai concetti relativi alla sicurezza, soprattutto in relazione WCF, vedere il set di modelli ed esercitazioni pratiche su MSDN all'indirizzo [scenari, modelli e linee guida di implementazione per Web Services Enhancements (WSE) 3.0](https://go.microsoft.com/fwlink/?LinkID=88250).  
  
 Programmazione della protezione WCF si basa su tre passaggi di impostazione degli elementi seguenti: la modalità di sicurezza, un tipo di credenziale client e i valori di credenziale. Questi passaggi possono essere eseguiti in codice o in configurazione.  
  
## <a name="setting-the-security-mode"></a>Impostazione della modalità di sicurezza  
 Di seguito vengono spiegati i passaggi generali per la programmazione con la modalità di sicurezza in WCF:  
  
1. Scegliere fra le associazioni predefinite un'associazione appropriata ai requisiti dell'applicazione. Per un elenco di associazioni disponibili, vedere [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md). Per impostazione predefinita, quasi tutte le associazioni presentano un meccanismo di sicurezza abilitato. L'unica eccezione è il <xref:System.ServiceModel.BasicHttpBinding> classe (usando la configurazione, il [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)).  
  
     L'associazione scelta determina il trasporto. Ad esempio, l'associazione <xref:System.ServiceModel.WSHttpBinding> utilizza il protocollo HTTP come trasporto, mentre l'associazione <xref:System.ServiceModel.NetTcpBinding> utilizza il trasporto TCP.  
  
2. Selezionare per l'associazione una delle modalità di sicurezza. Si noti che l'insieme delle modalità fra cui è possibile scegliere dipende dall'associazione scelta. Ad esempio, l'associazione <xref:System.ServiceModel.WSDualHttpBinding> non consente di scegliere la sicurezza a livello di trasporto. Analogamente, né l'associazione <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> né l'associazione <xref:System.ServiceModel.NetNamedPipeBinding> consentono di scegliere la sicurezza a livello di messaggio.  
  
     Sono disponibili tre opzioni:  
  
    1.  `Transport`  
  
         La sicurezza a livello di trasporto dipende dal meccanismo utilizzato dall'associazione scelta. Ad esempio, se si utilizza l'associazione `WSHttpBinding`, il meccanismo di sicurezza è Secure Sockets Layer (SSL), che peraltro è anche il meccanismo del protocollo HTTPS. In generale, il vantaggio principale della sicurezza a livello di trasporto è che offre una buona velocità effettiva indipendentemente dal trasporto utilizzato. Tuttavia, presenta due limitazioni: Il primo è che il meccanismo di trasporto determina il tipo di credenziale utilizzato per autenticare un utente. Di fatto ciò rappresenta uno svantaggio solo se un servizio deve garantire l'interoperabilità con altri servizi che richiedono vari tipi di credenziali. Inoltre, poiché la sicurezza non viene applicata a livello di messaggio, la sicurezza viene implementata in modo hop-by-hop anziché end-to-end. Questo secondo limite rappresenta un problema solo se il percorso dei messaggi fra client e servizio prevede intermediari. Per altre informazioni su quale trasporto utilizzare, vedere [scelta di un trasporto](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Per altre informazioni sull'uso di sicurezza del trasporto, vedere [Cenni preliminari sulla sicurezza di trasporto](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).  
  
    2.  `Message`  
  
         Nella sicurezza a livello di messaggio, ogni messaggio contiene le intestazioni e i dati necessari a garantire la sicurezza del messaggio. Poiché la composizione delle intestazioni è variabile, è possibile includere qualsiasi numero di credenziali. Ciò risulta essere un fattore rilevante se occorre interoperare con altri servizi che richiedono un tipo di credenziale specifico che un meccanismo di trasporto non è in grado di fornire, oppure se il messaggio deve essere utilizzato in più servizi, ognuno avente un requisito specifico di tipo di credenziale.  
  
         Per altre informazioni, vedere [protezione del messaggio](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).  
  
    3.  `TransportWithMessageCredential`  
  
         Questa scelta utilizza il livello di trasporto per proteggere il trasferimento dei messaggi, ognuno dei quali contiene le credenziali dettagliate richieste dagli altri servizi. Ciò combina il vantaggio in termini di prestazioni della sicurezza a livello di trasporto con il vantaggio delle credenziali dettagliate della sicurezza a livello di messaggio. Questa opzione è disponibile per le associazioni seguenti: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> e <xref:System.ServiceModel.WSHttpBinding>.  
  
3. Se si decide di utilizzare la sicurezza a livello di trasporto per il protocollo HTTP (ovvero il protocollo HTTPS), è inoltre necessario configurare l'host con un certificato SSL e quindi abilitare il protocollo SSL su una porta. Per altre informazioni, vedere [protezione del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
4. Se si utilizza l'associazione <xref:System.ServiceModel.WSHttpBinding> e non occorre stabilire una sessione protetta, impostare la proprietà <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> su `false`.  
  
     Una sessione protetta si verifica quando un client e un servizio creano un canale utilizzando una chiave simmetrica, ovvero quando sia il client sia il server utilizzano la stessa chiave per la durata della conversazione e fino alla chiusura del dialogo.  
  
## <a name="setting-the-client-credential-type"></a>Impostazione del tipo di credenziale client  
 Selezionare un tipo di credenziale client in base alle proprie esigenze. Per altre informazioni, vedere [la selezione di un tipo di credenziale](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md). Sono disponibili i tipi di credenziale client seguenti:  
  
-   `Windows`  
  
-   `Certificate`  
  
-   `Digest`  
  
-   `Basic`  
  
-   `UserName`  
  
-   `NTLM`  
  
-   `IssuedToken`  
  
 L'impostazione del tipo di credenziale dipende dalla modalità impostata. Se ad esempio è stata selezionata l'associazione `wsHttpBinding` e la modalità è stata impostata sulla sicurezza a livello di messaggio, l'attributo `clientCredentialType` dell'elemento Message può essere impostato su uno dei valori seguenti: `None`, `Windows`, `UserName`, `Certificate` e `IssuedToken`, come mostrato nell'esempio di configurazione seguente.  
  
```xml  
<system.serviceModel>  
<bindings>  
  <wsHttpBinding>  
    <binding name="myBinding">  
      <security mode="Message"/>  
      <message clientCredentialType="Windows"/>  
    </binding>  
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

- [Programmazione WCF di base](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [Scenari di sicurezza comuni](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
