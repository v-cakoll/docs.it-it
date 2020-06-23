---
title: 'Procedura: impostare la modalità di sicurezza'
description: 'Informazioni su come impostare le tre modalità di sicurezza WCF comuni per la maggior parte delle associazioni predefinite: Transport, Message e TransportWithMessageCredential.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 2f834e1930b7676592f6cbc29a577424d75ebc01
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244543"
---
# <a name="how-to-set-the-security-mode"></a>Procedura: impostare la modalità di sicurezza

Per la sicurezza Windows Communication Foundation (WCF) sono disponibili tre modalità di sicurezza comuni che si trovano nella maggior parte delle associazioni predefinite: trasporto, messaggio e "trasporto con credenziali messaggio". Esistono inoltre due modalità aggiuntive disponibili soltanto in due associazioni specifiche: la modalità "Solo credenziale a livello di trasporto" ("TransportCredentialOnly") dell'associazione <xref:System.ServiceModel.BasicHttpBinding> e la modalità "Entrambi" ("Both") dell'associazione <xref:System.ServiceModel.NetMsmqBinding>. Tuttavia, questo argomento descrive solo le tre modalità di sicurezza generali, ovvero: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message> e <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.

Si noti che non tutte le associazioni predefinite supportano queste modalità. Questo argomento descrive come utilizzare le classi <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.NetTcpBinding> per impostare la modalità, sia a livello di programmazione sia in configurazione.

Per altre informazioni, vedere sicurezza WCF, vedere [Panoramica della sicurezza](./feature-details/security-overview.md), protezione [dei servizi](securing-services.md)e [protezione di servizi e client](./feature-details/securing-services-and-clients.md). Per ulteriori informazioni sulla modalità trasporto e il messaggio, vedere [sicurezza del trasporto](./feature-details/transport-security.md) e sicurezza dei [messaggi](./feature-details/message-security-in-wcf.md).

## <a name="to-set-the-security-mode-in-code"></a>Per impostare la modalità di sicurezza in codice

1. Creare un'istanza della classe di associazione in uso. Per un elenco di associazioni predefinite, vedere [associazioni fornite dal sistema](system-provided-bindings.md). In questo esempio viene creata un'istanza della classe <xref:System.ServiceModel.WSHttpBinding>

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

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a>Per impostare la proprietà ClientCredentialType quando si imposta la modalità "Transport"

1. Creare un'istanza dell'associazione.

2. Impostare la proprietà `Mode` su `Transport`.

3. Impostare la proprietà `ClientCredential` su un valore appropriato. Nell'esempio di codice seguente la proprietà viene impostata su `Windows`.

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a>Per impostare la proprietà ClientCredentialType quando si imposta la modalità "Message"

1. Creare un'istanza dell'associazione.

2. Impostare la proprietà `Mode` su `Message`.

3. Impostare la proprietà `ClientCredential` su un valore appropriato. Nell'esempio di codice seguente la proprietà viene impostata su `Certificate`.

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a>Per impostare la modalità e la proprietà ClientCredentialType in configurazione

1. Aggiungere un elemento di associazione appropriato all' [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione. Nell'esempio seguente viene aggiunto un [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.

2. Aggiungere un `<binding>` elemento e impostare il relativo `name` attributo su un valore appropriato.

3. Aggiungere un elemento `<security>``mode``Message``Transport`.

4. Se si imposta la modalità su `Transport`, aggiungere un elemento `<transport>` su un valore appropriato.

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

Per altre informazioni, vedere [procedura: usare la sicurezza del trasporto e le credenziali del messaggio](./feature-details/how-to-use-transport-security-and-message-credentials.md).

## <a name="see-also"></a>Vedere anche

- [Procedura: configurare una porta con un certificato SSL](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [Procedura: usare le funzionalità di sicurezza a livello di trasporto e le credenziali a livello di messaggio](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [Sicurezza del trasporto](./feature-details/transport-security.md)
- [Sicurezza dei messaggi](./feature-details/message-security-in-wcf.md)
- [Panoramica della sicurezza](./feature-details/security-overview.md)
- [Associazioni fornite dal sistema](system-provided-bindings.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
