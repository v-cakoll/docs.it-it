---
title: 'Procedura: impostare la modalità di sicurezza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
author: BrucePerlerMS
ms.openlocfilehash: 32fd1ebede841488d1bfabd2f92bd3fb1ffb55e8
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035656"
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="80a8d-102">Procedura: impostare la modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="80a8d-102">How to: Set the Security Mode</span></span>
<span data-ttu-id="80a8d-103">Sicurezza di Windows Communication Foundation (WCF) dispone di tre modalità di sicurezza comuni che si trovano nelle associazioni predefinite più: il trasporto e messaggio "trasporto con credenziali del messaggio".</span><span class="sxs-lookup"><span data-stu-id="80a8d-103">Windows Communication Foundation (WCF) security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="80a8d-104">Esistono inoltre due modalità aggiuntive disponibili soltanto in due associazioni specifiche: la modalità "Solo credenziale a livello di trasporto" ("TransportCredentialOnly") dell'associazione <xref:System.ServiceModel.BasicHttpBinding> e la modalità "Entrambi" ("Both") dell'associazione <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="80a8d-104">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="80a8d-105">Tuttavia, questo argomento descrive solo le tre modalità di sicurezza generali, ovvero: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message> e <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="80a8d-105">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
 <span data-ttu-id="80a8d-106">Si noti che non tutte le associazioni predefinite supportano queste modalità.</span><span class="sxs-lookup"><span data-stu-id="80a8d-106">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="80a8d-107">Questo argomento descrive come utilizzare le classi <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.NetTcpBinding> per impostare la modalità, sia a livello di programmazione sia in configurazione.</span><span class="sxs-lookup"><span data-stu-id="80a8d-107">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>  
  
 <span data-ttu-id="80a8d-108">Per altre informazioni, vedere sicurezza WCF, vedere [Panoramica della sicurezza](../../../docs/framework/wcf/feature-details/security-overview.md), [Securing Services](../../../docs/framework/wcf/securing-services.md), e [Securing Services and Clients](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="80a8d-108">For more information, see WCF security, see [Security Overview](../../../docs/framework/wcf/feature-details/security-overview.md), [Securing Services](../../../docs/framework/wcf/securing-services.md), and [Securing Services and Clients](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="80a8d-109">Per altre informazioni sulle modalità di trasporto e messaggio, vedere [la sicurezza del trasporto](../../../docs/framework/wcf/feature-details/transport-security.md) e [Message Security](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="80a8d-109">For more information about transport mode and message, see [Transport Security](../../../docs/framework/wcf/feature-details/transport-security.md) and [Message Security](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span></span>  
  
### <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="80a8d-110">Per impostare la modalità di sicurezza in codice</span><span class="sxs-lookup"><span data-stu-id="80a8d-110">To set the security mode in code</span></span>  
  
1.  <span data-ttu-id="80a8d-111">Creare un'istanza della classe di associazione in uso.</span><span class="sxs-lookup"><span data-stu-id="80a8d-111">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="80a8d-112">Per un elenco di associazioni predefinite, vedere [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="80a8d-112">For a list of predefined bindings, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="80a8d-113">In questo esempio viene creata un'istanza della classe <xref:System.ServiceModel.WSHttpBinding></span><span class="sxs-lookup"><span data-stu-id="80a8d-113">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
2.  <span data-ttu-id="80a8d-114">Impostare la proprietà `Mode` dell'oggetto restituito dalla proprietà `Security`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-114">Set the `Mode` property of the object returned by the `Security` property.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     <span data-ttu-id="80a8d-115">In alternativa, impostare la modalità su "Message", come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="80a8d-115">Alternatively, set the mode to message, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     <span data-ttu-id="80a8d-116">In alternativa, impostare la modalità su "TransportWithMessageCredential", come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="80a8d-116">Or set the mode to transport with message credentials, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3.  <span data-ttu-id="80a8d-117">La modalità può anche essere impostata nel costruttore dell'associazione, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="80a8d-117">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="80a8d-118">Impostazione della proprietà ClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="80a8d-118">Setting the ClientCredentialType Property</span></span>  
 <span data-ttu-id="80a8d-119">L'impostazione della modalità su uno dei tre valori determina il valore su cui impostare la proprietà che specifica il tipo di credenziale client, ovvero `ClientCredentialType`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-119">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="80a8d-120">Ad esempio, se si utilizza la classe <xref:System.ServiceModel.WSHttpBinding> e si imposta la modalità su `Transport`, occorre impostare la proprietà <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> della classe <xref:System.ServiceModel.HttpTransportSecurity> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="80a8d-120">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>  
  
#### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="80a8d-121">Per impostare la proprietà ClientCredentialType quando si imposta la modalità "Transport"</span><span class="sxs-lookup"><span data-stu-id="80a8d-121">To set the ClientCredentialType property for Transport mode</span></span>  
  
1.  <span data-ttu-id="80a8d-122">Creare un'istanza dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="80a8d-122">Create an instance of the binding.</span></span>  
  
2.  <span data-ttu-id="80a8d-123">Impostare la proprietà `Mode` su `Transport`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-123">Set the `Mode` property to `Transport`.</span></span>  
  
3.  <span data-ttu-id="80a8d-124">Impostare la proprietà `ClientCredential` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="80a8d-124">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="80a8d-125">Nell'esempio di codice seguente la proprietà viene impostata su `Windows`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-125">The following code sets the property to `Windows`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="80a8d-126">Per impostare la proprietà ClientCredentialType quando si imposta la modalità "Message"</span><span class="sxs-lookup"><span data-stu-id="80a8d-126">To set the ClientCredentialType property for Message mode</span></span>  
  
1.  <span data-ttu-id="80a8d-127">Creare un'istanza dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="80a8d-127">Create an instance of the binding.</span></span>  
  
2.  <span data-ttu-id="80a8d-128">Impostare la proprietà `Mode` su `Message`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-128">Set the `Mode` property to `Message`.</span></span>  
  
3.  <span data-ttu-id="80a8d-129">Impostare la proprietà `ClientCredential` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="80a8d-129">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="80a8d-130">Nell'esempio di codice seguente la proprietà viene impostata su `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-130">The following code sets the property to `Certificate`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="80a8d-131">Per impostare la modalità e la proprietà ClientCredentialType in configurazione</span><span class="sxs-lookup"><span data-stu-id="80a8d-131">To set the Mode and ClientCredentialType property in configuration</span></span>  
  
1.  <span data-ttu-id="80a8d-132">Aggiungere un elemento di binding appropriato per il [ \<associazioni >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="80a8d-132">Add an appropriate binding element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="80a8d-133">L'esempio seguente aggiunge un [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="80a8d-133">The following example adds a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
2.  <span data-ttu-id="80a8d-134">Aggiungere un `<binding>` e impostare il `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="80a8d-134">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="80a8d-135">Aggiungere un `<security>` elemento e impostare il `mode` attributo `Message`, `Transport`, o `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-135">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>  
  
4.  <span data-ttu-id="80a8d-136">Se si imposta la modalità su `Transport`, aggiungere un elemento `<transport>` e impostare l'attributo `clientCredential` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="80a8d-136">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>  
  
     <span data-ttu-id="80a8d-137">Nell'esempio seguente, la modalità viene impostata su "`Transport"`, quindi l'attributo `clientCredentialType` dell'elemento `<transport>` viene impostato su "`Windows"`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-137">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" />  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="80a8d-138">In alternativa, impostare la `security mode` su "`Message"` seguita da un elemento `<"message">`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-138">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="80a8d-139">In questo esempio l'attributo `clientCredentialType` viene impostato su "`Certificate"`.</span><span class="sxs-lookup"><span data-stu-id="80a8d-139">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="80a8d-140">L'utilizzo del valore <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> rappresenta un caso speciale e viene spiegato di seguito.</span><span class="sxs-lookup"><span data-stu-id="80a8d-140">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>  
  
### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="80a8d-141">Utilizzo della modalità TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="80a8d-141">Using TransportWithMessageCredential</span></span>  
 <span data-ttu-id="80a8d-142">Quando si imposta la modalità di sicurezza su `TransportWithMessageCredential`, il trasporto determina il meccanismo di sicurezza a livello di trasporto effettivamente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="80a8d-142">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="80a8d-143">Ad esempio, il protocollo di trasporto HTTP utilizza il meccanismo Secure Sockets Layer (SSL) su HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="80a8d-143">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="80a8d-144">Pertanto, l'impostazione della proprietà `ClientCredentialType` di qualsiasi oggetto di sicurezza a livello di trasporto (ad esempio <xref:System.ServiceModel.HttpTransportSecurity>) viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="80a8d-144">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="80a8d-145">In altre parole, è possibile impostare solo la proprietà `ClientCredentialType` dell'oggetto di sicurezza a livello di messaggio (per l'associazione `WSHttpBinding`, tale proprietà può essere impostata solo per l'oggetto <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>).</span><span class="sxs-lookup"><span data-stu-id="80a8d-145">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>  
  
 <span data-ttu-id="80a8d-146">Per altre informazioni, vedere [procedura: usare la sicurezza trasporto e le credenziali del messaggio](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="80a8d-146">For more information, see [How to: Use Transport Security and Message Credentials](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a8d-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80a8d-147">See Also</span></span>  
 [<span data-ttu-id="80a8d-148">Procedura: Configurare una porta con un certificato SSL</span><span class="sxs-lookup"><span data-stu-id="80a8d-148">How to: Configure a Port with an SSL Certificate</span></span>](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="80a8d-149">Procedura: Usare le funzionalità di sicurezza del trasporto e le credenziali a livello di messaggio</span><span class="sxs-lookup"><span data-stu-id="80a8d-149">How to: Use Transport Security and Message Credentials</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)  
 [<span data-ttu-id="80a8d-150">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="80a8d-150">Transport Security</span></span>](../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="80a8d-151">Sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="80a8d-151">Message Security</span></span>](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [<span data-ttu-id="80a8d-152">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="80a8d-152">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="80a8d-153">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="80a8d-153">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="80a8d-154">\<security></span><span class="sxs-lookup"><span data-stu-id="80a8d-154">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)  
 [<span data-ttu-id="80a8d-155">\<security></span><span class="sxs-lookup"><span data-stu-id="80a8d-155">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)  
 [<span data-ttu-id="80a8d-156">\<security></span><span class="sxs-lookup"><span data-stu-id="80a8d-156">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
