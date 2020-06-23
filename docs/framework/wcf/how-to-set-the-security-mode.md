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
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="9e70a-103">Procedura: impostare la modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9e70a-103">How to: Set the Security Mode</span></span>

<span data-ttu-id="9e70a-104">Per la sicurezza Windows Communication Foundation (WCF) sono disponibili tre modalità di sicurezza comuni che si trovano nella maggior parte delle associazioni predefinite: trasporto, messaggio e "trasporto con credenziali messaggio".</span><span class="sxs-lookup"><span data-stu-id="9e70a-104">Windows Communication Foundation (WCF) security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="9e70a-105">Esistono inoltre due modalità aggiuntive disponibili soltanto in due associazioni specifiche: la modalità "Solo credenziale a livello di trasporto" ("TransportCredentialOnly") dell'associazione <xref:System.ServiceModel.BasicHttpBinding> e la modalità "Entrambi" ("Both") dell'associazione <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="9e70a-105">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="9e70a-106">Tuttavia, questo argomento descrive solo le tre modalità di sicurezza generali, ovvero: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message> e <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="9e70a-106">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>

<span data-ttu-id="9e70a-107">Si noti che non tutte le associazioni predefinite supportano queste modalità.</span><span class="sxs-lookup"><span data-stu-id="9e70a-107">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="9e70a-108">Questo argomento descrive come utilizzare le classi <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.NetTcpBinding> per impostare la modalità, sia a livello di programmazione sia in configurazione.</span><span class="sxs-lookup"><span data-stu-id="9e70a-108">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>

<span data-ttu-id="9e70a-109">Per altre informazioni, vedere sicurezza WCF, vedere [Panoramica della sicurezza](./feature-details/security-overview.md), protezione [dei servizi](securing-services.md)e [protezione di servizi e client](./feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9e70a-109">For more information, see WCF security, see [Security Overview](./feature-details/security-overview.md), [Securing Services](securing-services.md), and [Securing Services and Clients](./feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="9e70a-110">Per ulteriori informazioni sulla modalità trasporto e il messaggio, vedere [sicurezza del trasporto](./feature-details/transport-security.md) e sicurezza dei [messaggi](./feature-details/message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="9e70a-110">For more information about transport mode and message, see [Transport Security](./feature-details/transport-security.md) and [Message Security](./feature-details/message-security-in-wcf.md).</span></span>

## <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="9e70a-111">Per impostare la modalità di sicurezza in codice</span><span class="sxs-lookup"><span data-stu-id="9e70a-111">To set the security mode in code</span></span>

1. <span data-ttu-id="9e70a-112">Creare un'istanza della classe di associazione in uso.</span><span class="sxs-lookup"><span data-stu-id="9e70a-112">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="9e70a-113">Per un elenco di associazioni predefinite, vedere [associazioni fornite dal sistema](system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="9e70a-113">For a list of predefined bindings, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="9e70a-114">In questo esempio viene creata un'istanza della classe <xref:System.ServiceModel.WSHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9e70a-114">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>

2. <span data-ttu-id="9e70a-115">Impostare la proprietà `Mode` dell'oggetto restituito dalla proprietà `Security`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-115">Set the `Mode` property of the object returned by the `Security` property.</span></span>

     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]

     <span data-ttu-id="9e70a-116">In alternativa, impostare la modalità su "Message", come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9e70a-116">Alternatively, set the mode to message, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]

     <span data-ttu-id="9e70a-117">In alternativa, impostare la modalità su "TransportWithMessageCredential", come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9e70a-117">Or set the mode to transport with message credentials, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]

3. <span data-ttu-id="9e70a-118">La modalità può anche essere impostata nel costruttore dell'associazione, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9e70a-118">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]

## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="9e70a-119">Impostazione della proprietà ClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9e70a-119">Setting the ClientCredentialType Property</span></span>

<span data-ttu-id="9e70a-120">L'impostazione della modalità su uno dei tre valori determina il valore su cui impostare la proprietà che specifica il tipo di credenziale client, ovvero `ClientCredentialType`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-120">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="9e70a-121">Ad esempio, se si utilizza la classe <xref:System.ServiceModel.WSHttpBinding> e si imposta la modalità su `Transport`, occorre impostare la proprietà <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> della classe <xref:System.ServiceModel.HttpTransportSecurity> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="9e70a-121">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="9e70a-122">Per impostare la proprietà ClientCredentialType quando si imposta la modalità "Transport"</span><span class="sxs-lookup"><span data-stu-id="9e70a-122">To set the ClientCredentialType property for Transport mode</span></span>

1. <span data-ttu-id="9e70a-123">Creare un'istanza dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="9e70a-123">Create an instance of the binding.</span></span>

2. <span data-ttu-id="9e70a-124">Impostare la proprietà `Mode` su `Transport`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-124">Set the `Mode` property to `Transport`.</span></span>

3. <span data-ttu-id="9e70a-125">Impostare la proprietà `ClientCredential` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="9e70a-125">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="9e70a-126">Nell'esempio di codice seguente la proprietà viene impostata su `Windows`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-126">The following code sets the property to `Windows`.</span></span>

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="9e70a-127">Per impostare la proprietà ClientCredentialType quando si imposta la modalità "Message"</span><span class="sxs-lookup"><span data-stu-id="9e70a-127">To set the ClientCredentialType property for Message mode</span></span>

1. <span data-ttu-id="9e70a-128">Creare un'istanza dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="9e70a-128">Create an instance of the binding.</span></span>

2. <span data-ttu-id="9e70a-129">Impostare la proprietà `Mode` su `Message`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-129">Set the `Mode` property to `Message`.</span></span>

3. <span data-ttu-id="9e70a-130">Impostare la proprietà `ClientCredential` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="9e70a-130">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="9e70a-131">Nell'esempio di codice seguente la proprietà viene impostata su `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-131">The following code sets the property to `Certificate`.</span></span>

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="9e70a-132">Per impostare la modalità e la proprietà ClientCredentialType in configurazione</span><span class="sxs-lookup"><span data-stu-id="9e70a-132">To set the Mode and ClientCredentialType property in configuration</span></span>

1. <span data-ttu-id="9e70a-133">Aggiungere un elemento di associazione appropriato all' [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9e70a-133">Add an appropriate binding element to the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="9e70a-134">Nell'esempio seguente viene aggiunto un [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="9e70a-134">The following example adds a [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

2. <span data-ttu-id="9e70a-135">Aggiungere un `<binding>` elemento e impostare il relativo `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="9e70a-135">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="9e70a-136">Aggiungere un elemento `<security>``mode``Message``Transport`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-136">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

4. <span data-ttu-id="9e70a-137">Se si imposta la modalità su `Transport`, aggiungere un elemento `<transport>` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="9e70a-137">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>

     <span data-ttu-id="9e70a-138">Nell'esempio seguente, la modalità viene impostata su "`Transport"`, quindi l'attributo `clientCredentialType` dell'elemento `<transport>` viene impostato su "`Windows"`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-138">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="TransportSecurity">
        <security mode="Transport" >
           <transport clientCredentialType = "Windows" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="9e70a-139">In alternativa, impostare la `security mode` su "`Message"` seguita da un elemento `<"message">`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-139">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="9e70a-140">In questo esempio l'attributo `clientCredentialType` viene impostato su "`Certificate"`.</span><span class="sxs-lookup"><span data-stu-id="9e70a-140">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="MessageSecurity">
        <security mode="Message" >
           <message clientCredentialType = "Certificate" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="9e70a-141">L'utilizzo del valore <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> rappresenta un caso speciale e viene spiegato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9e70a-141">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>

### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="9e70a-142">Utilizzo della modalità TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="9e70a-142">Using TransportWithMessageCredential</span></span>

<span data-ttu-id="9e70a-143">Quando si imposta la modalità di sicurezza su `TransportWithMessageCredential`, il trasporto determina il meccanismo di sicurezza a livello di trasporto effettivamente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9e70a-143">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="9e70a-144">Ad esempio, il protocollo di trasporto HTTP utilizza il meccanismo Secure Sockets Layer (SSL) su HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="9e70a-144">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="9e70a-145">Pertanto, l'impostazione della proprietà `ClientCredentialType` di qualsiasi oggetto di sicurezza a livello di trasporto (ad esempio <xref:System.ServiceModel.HttpTransportSecurity>) viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="9e70a-145">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="9e70a-146">In altre parole, è possibile impostare solo la proprietà `ClientCredentialType` dell'oggetto di sicurezza a livello di messaggio (per l'associazione `WSHttpBinding`, tale proprietà può essere impostata solo per l'oggetto <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>).</span><span class="sxs-lookup"><span data-stu-id="9e70a-146">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>

<span data-ttu-id="9e70a-147">Per altre informazioni, vedere [procedura: usare la sicurezza del trasporto e le credenziali del messaggio](./feature-details/how-to-use-transport-security-and-message-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="9e70a-147">For more information, see [How to: Use Transport Security and Message Credentials](./feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e70a-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e70a-148">See also</span></span>

- [<span data-ttu-id="9e70a-149">Procedura: configurare una porta con un certificato SSL</span><span class="sxs-lookup"><span data-stu-id="9e70a-149">How to: Configure a Port with an SSL Certificate</span></span>](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="9e70a-150">Procedura: usare le funzionalità di sicurezza a livello di trasporto e le credenziali a livello di messaggio</span><span class="sxs-lookup"><span data-stu-id="9e70a-150">How to: Use Transport Security and Message Credentials</span></span>](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [<span data-ttu-id="9e70a-151">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="9e70a-151">Transport Security</span></span>](./feature-details/transport-security.md)
- [<span data-ttu-id="9e70a-152">Sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="9e70a-152">Message Security</span></span>](./feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="9e70a-153">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="9e70a-153">Security Overview</span></span>](./feature-details/security-overview.md)
- [<span data-ttu-id="9e70a-154">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="9e70a-154">System-Provided Bindings</span></span>](system-provided-bindings.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
