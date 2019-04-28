---
title: 'Procedura: Impostare la modalità di sicurezza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 5a4550e4c914dcdbc9908e766c67a2efa53e6e9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928895"
---
# <a name="how-to-set-the-security-mode"></a>Procedura: Impostare la modalità di sicurezza
Sicurezza di Windows Communication Foundation (WCF) dispone di tre modalità di sicurezza comuni che si trovano nelle associazioni predefinite più: il trasporto e messaggio "trasporto con credenziali del messaggio". Esistono inoltre due modalità aggiuntive disponibili soltanto in due associazioni specifiche: la modalità "Solo credenziale a livello di trasporto" ("TransportCredentialOnly") dell'associazione <xref:System.ServiceModel.BasicHttpBinding> e la modalità "Entrambi" ("Both") dell'associazione <xref:System.ServiceModel.NetMsmqBinding>. Tuttavia, questo argomento descrive solo le tre modalità di sicurezza generali, ovvero: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message> e <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.  
  
 Si noti che non tutte le associazioni predefinite supportano queste modalità. Questo argomento descrive come utilizzare le classi <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.NetTcpBinding> per impostare la modalità, sia a livello di programmazione sia in configurazione.  
  
 Per altre informazioni, vedere sicurezza WCF, vedere [Panoramica della sicurezza](../../../docs/framework/wcf/feature-details/security-overview.md), [Securing Services](../../../docs/framework/wcf/securing-services.md), e [Securing Services and Clients](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md). Per altre informazioni sulle modalità di trasporto e messaggio, vedere [la sicurezza del trasporto](../../../docs/framework/wcf/feature-details/transport-security.md) e [Message Security](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).  
  
### <a name="to-set-the-security-mode-in-code"></a>Per impostare la modalità di sicurezza in codice  
  
1. Creare un'istanza della classe di associazione in uso. Per un elenco di associazioni predefinite, vedere [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md). In questo esempio viene creata un'istanza della classe <xref:System.ServiceModel.WSHttpBinding>  
  
2. Impostare la proprietà `Mode` dell'oggetto restituito dalla proprietà `Security`.  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     In alternativa, impostare la modalità su "Message", come mostrato nel codice seguente.  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     In alternativa, impostare la modalità su "TransportWithMessageCredential", come mostrato nel codice seguente.  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3. La modalità può anche essere impostata nel costruttore dell'associazione, come mostrato nel codice seguente.  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## <a name="setting-the-clientcredentialtype-property"></a>Impostazione della proprietà ClientCredentialType  
 L'impostazione della modalità su uno dei tre valori determina il valore su cui impostare la proprietà che specifica il tipo di credenziale client, ovvero `ClientCredentialType`. Ad esempio, se si utilizza la classe <xref:System.ServiceModel.WSHttpBinding> e si imposta la modalità su `Transport`, occorre impostare la proprietà <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> della classe <xref:System.ServiceModel.HttpTransportSecurity> su un valore appropriato.  
  
#### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a>Per impostare la proprietà ClientCredentialType quando si imposta la modalità "Transport"  
  
1. Creare un'istanza dell'associazione.  
  
2. Impostare la proprietà `Mode` su `Transport`.  
  
3. Impostare la proprietà `ClientCredential` su un valore appropriato. Nell'esempio di codice seguente la proprietà viene impostata su `Windows`.  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a>Per impostare la proprietà ClientCredentialType quando si imposta la modalità "Message"  
  
1. Creare un'istanza dell'associazione.  
  
2. Impostare la proprietà `Mode` su `Message`.  
  
3. Impostare la proprietà `ClientCredential` su un valore appropriato. Nell'esempio di codice seguente la proprietà viene impostata su `Certificate`.  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a>Per impostare la modalità e la proprietà ClientCredentialType in configurazione  
  
1. Aggiungere un elemento di binding appropriato per il [ \<associazioni >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione. L'esempio seguente aggiunge un [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.  
  
2. Aggiungere un `<binding>` e impostare il `name` attributo su un valore appropriato.  
  
3. Aggiungere un `<security>` elemento e impostare il `mode` attributo `Message`, `Transport`, o `TransportWithMessageCredential`.  
  
4. Se si imposta la modalità su `Transport`, aggiungere un elemento `<transport>` e impostare l'attributo `clientCredential` su un valore appropriato.  
  
     Nell'esempio seguente, la modalità viene impostata su "`Transport"`, quindi l'attributo `clientCredentialType` dell'elemento `<transport>` viene impostato su "`Windows"`.  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" >  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     In alternativa, impostare la `security mode` su "`Message"` seguita da un elemento `<"message">`. In questo esempio l'attributo `clientCredentialType` viene impostato su "`Certificate"`.  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" >  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     L'utilizzo del valore <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> rappresenta un caso speciale e viene spiegato di seguito.  
  
### <a name="using-transportwithmessagecredential"></a>Utilizzo della modalità TransportWithMessageCredential  
 Quando si imposta la modalità di sicurezza su `TransportWithMessageCredential`, il trasporto determina il meccanismo di sicurezza a livello di trasporto effettivamente utilizzato. Ad esempio, il protocollo di trasporto HTTP utilizza il meccanismo Secure Sockets Layer (SSL) su HTTP (HTTPS). Pertanto, l'impostazione della proprietà `ClientCredentialType` di qualsiasi oggetto di sicurezza a livello di trasporto (ad esempio <xref:System.ServiceModel.HttpTransportSecurity>) viene ignorata.  In altre parole, è possibile impostare solo la proprietà `ClientCredentialType` dell'oggetto di sicurezza a livello di messaggio (per l'associazione `WSHttpBinding`, tale proprietà può essere impostata solo per l'oggetto <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>).  
  
 Per altre informazioni, vedere [Procedura: Usare la sicurezza trasporto e le credenziali del messaggio](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Configurare una porta con un certificato SSL](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [Procedura: Usare la sicurezza trasporto e le credenziali del messaggio](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)
- [Sicurezza del trasporto](../../../docs/framework/wcf/feature-details/transport-security.md)
- [Sicurezza dei messaggi](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [Panoramica della sicurezza](../../../docs/framework/wcf/feature-details/security-overview.md)
- [Associazioni fornite dal sistema](../../../docs/framework/wcf/system-provided-bindings.md)
- [\<security>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [\<security>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [\<security>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
