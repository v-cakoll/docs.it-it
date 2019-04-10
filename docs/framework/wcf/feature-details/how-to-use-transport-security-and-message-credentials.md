---
title: 'Procedura: Usare la sicurezza del trasporto e le credenziali per il messaggio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
ms.openlocfilehash: f9c90ac93a27f90479ee7225f62afb98a5000fe9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321478"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="29d49-102">Procedura: Usare la sicurezza del trasporto e le credenziali per il messaggio</span><span class="sxs-lookup"><span data-stu-id="29d49-102">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="29d49-103">Protezione di un servizio con le credenziali di trasporto e messaggio utilizza il meglio delle modalità di sicurezza di trasporto e messaggio di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="29d49-103">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="29d49-104">Complessivamente, le funzionalità di sicurezza a livello di trasporto garantiscono integrità e riservatezza, mentre le funzionalità di sicurezza a livello di messaggio offrono vari tipi di credenziali non disponibili quando si utilizzano meccanismi di sicurezza basati esclusivamente sul livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="29d49-104">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="29d49-105">In questo argomento vengono illustrati i passaggi di base per implementare il trasporto con credenziali messaggio utilizzando le associazioni <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="29d49-105">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> <span data-ttu-id="29d49-106">Per altre informazioni sull'impostazione della modalità di sicurezza, vedere [come: Impostare la modalità di sicurezza](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="29d49-106">For more information about setting the security mode, see [How to: Set the Security Mode](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="29d49-107">Quando si imposta la modalità di sicurezza su `TransportWithMessageCredential`, il trasporto determina il meccanismo di sicurezza a livello di trasporto effettivamente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="29d49-107">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="29d49-108">Nel caso del protocollo HTTP, il meccanismo è Secure Sockets Layer (SSL) su HTTP (HTTPS). Nel caso del protocollo TCP, invece, il meccanismo è SSL su TCP oppure Windows.</span><span class="sxs-lookup"><span data-stu-id="29d49-108">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="29d49-109">Se il trasporto è HTTP (tramite l'associazione <xref:System.ServiceModel.WSHttpBinding>), il protocollo HTTPS fornisce la protezione a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="29d49-109">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="29d49-110">In tal caso è necessario configurare il computer che ospita il servizio con un certificato SSL associato a una porta, come mostrato in seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="29d49-110">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="29d49-111">Se il trasporto è TCP (tramite l'associazione <xref:System.ServiceModel.NetTcpBinding>), per impostazione predefinita la protezione a livello di trasporto fornita è la protezione di Windows oppure SSL su TCP.</span><span class="sxs-lookup"><span data-stu-id="29d49-111">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="29d49-112">Quando si utilizza SSL su TCP è necessario utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> per specificare il certificato, come mostrato in seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="29d49-112">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="29d49-113">Per utilizzare l'associazione WSHttpBinding con un certificato allo scopo di fornire la protezione a livello di trasporto (in codice)</span><span class="sxs-lookup"><span data-stu-id="29d49-113">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="29d49-114">Usare lo strumento HttpCfg.exe per associare un certificato SSL a una porta del computer.</span><span class="sxs-lookup"><span data-stu-id="29d49-114">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> <span data-ttu-id="29d49-115">Per altre informazioni, vedere [Procedura: Configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="29d49-115">For more information, see [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2. <span data-ttu-id="29d49-116">Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostare la proprietà <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> su <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="29d49-116">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3. <span data-ttu-id="29d49-117">Impostare la proprietà <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-117">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="29d49-118">(Per altre informazioni, vedere [la selezione di un tipo di credenziale](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) Nel codice seguente viene utilizzato il valore <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="29d49-118">(For more information, see [Selecting a Credential Type](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="29d49-119">Creare un'istanza della classe <xref:System.Uri> con un indirizzo di base appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-119">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="29d49-120">Si noti che l'indirizzo deve utilizzare lo schema "HTTPS" e deve contenere il nome effettivo del computer e il numero della porta a cui il certificato SSL è associato.</span><span class="sxs-lookup"><span data-stu-id="29d49-120">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="29d49-121">In alternativa è possibile impostare l'indirizzo di base in configurazione.</span><span class="sxs-lookup"><span data-stu-id="29d49-121">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="29d49-122">Aggiungere un endpoint di servizio tramite il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="29d49-122">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6. <span data-ttu-id="29d49-123">Creare l'istanza della classe <xref:System.ServiceModel.ServiceHost> e chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="29d49-123">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="29d49-124">Per utilizzare l'associazione NetTcpBinding con un certificato allo scopo di fornire la protezione a livello di trasporto (in codice)</span><span class="sxs-lookup"><span data-stu-id="29d49-124">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="29d49-125">Creare un'istanza della classe <xref:System.ServiceModel.NetTcpBinding> e impostare la proprietà <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> su <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="29d49-125">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="29d49-126">Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-126">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="29d49-127">Nel codice seguente viene utilizzato il valore <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="29d49-127">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3. <span data-ttu-id="29d49-128">Creare un'istanza della classe <xref:System.Uri> con un indirizzo di base appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-128">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="29d49-129">Si noti che l'indirizzo deve utilizzare lo schema "net.tcp".</span><span class="sxs-lookup"><span data-stu-id="29d49-129">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="29d49-130">In alternativa è possibile impostare l'indirizzo di base in configurazione.</span><span class="sxs-lookup"><span data-stu-id="29d49-130">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4. <span data-ttu-id="29d49-131">Creare l'istanza della classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="29d49-131">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5. <span data-ttu-id="29d49-132">Utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> per impostare in modo esplicito il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="29d49-132">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6. <span data-ttu-id="29d49-133">Aggiungere un endpoint di servizio tramite il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="29d49-133">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7. <span data-ttu-id="29d49-134">Chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="29d49-134">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="29d49-135">Per utilizzare l'associazione NetTcpBinding con Windows allo scopo di fornire la protezione a livello di trasporto (in codice)</span><span class="sxs-lookup"><span data-stu-id="29d49-135">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1. <span data-ttu-id="29d49-136">Creare un'istanza della classe <xref:System.ServiceModel.NetTcpBinding> e impostare la proprietà <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> su <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="29d49-136">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="29d49-137">Impostare la protezione a livello di trasporto in modo che utilizzi Windows. A tale scopo, impostare la proprietà <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> su <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span><span class="sxs-lookup"><span data-stu-id="29d49-137">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="29d49-138">Si noti che questo valore è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29d49-138">(Note that this is the default.)</span></span>  
  
3. <span data-ttu-id="29d49-139">Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-139">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="29d49-140">Nel codice seguente viene utilizzato il valore <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="29d49-140">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="29d49-141">Creare un'istanza della classe <xref:System.Uri> con un indirizzo di base appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-141">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="29d49-142">Si noti che l'indirizzo deve utilizzare lo schema "net.tcp".</span><span class="sxs-lookup"><span data-stu-id="29d49-142">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="29d49-143">In alternativa è possibile impostare l'indirizzo di base in configurazione.</span><span class="sxs-lookup"><span data-stu-id="29d49-143">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="29d49-144">Creare l'istanza della classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="29d49-144">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6. <span data-ttu-id="29d49-145">Utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> per impostare in modo esplicito il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="29d49-145">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7. <span data-ttu-id="29d49-146">Aggiungere un endpoint di servizio tramite il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="29d49-146">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8. <span data-ttu-id="29d49-147">Chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="29d49-147">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="29d49-148">Utilizzo della configurazione</span><span class="sxs-lookup"><span data-stu-id="29d49-148">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="29d49-149">Per utilizzare l'associazione WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="29d49-149">To use the WSHttpBinding</span></span>  
  
1. <span data-ttu-id="29d49-150">Configurare il computer con un certificato SSL associato a una porta.</span><span class="sxs-lookup"><span data-stu-id="29d49-150">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="29d49-151">(Per altre informazioni, vedere [come: Configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)).</span><span class="sxs-lookup"><span data-stu-id="29d49-151">(For more information, see [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="29d49-152">Non è necessario impostare una <`transport`> valore dell'elemento con questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="29d49-152">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2. <span data-ttu-id="29d49-153">Specificare il tipo di credenziale client della protezione a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="29d49-153">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="29d49-154">L'esempio seguente imposta la `clientCredentialType` attributo del <`message`> elemento `UserName`.</span><span class="sxs-lookup"><span data-stu-id="29d49-154">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="29d49-155">Per utilizzare l'associazione NetTcpBinding con un certificato allo scopo di fornire la protezione a livello di trasporto</span><span class="sxs-lookup"><span data-stu-id="29d49-155">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1. <span data-ttu-id="29d49-156">Nel caso di SSL su TCP occorre specificare in modo esplicito il certificato nell'elemento `<behaviors>`.</span><span class="sxs-lookup"><span data-stu-id="29d49-156">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="29d49-157">Nell'esempio seguente viene individuato un certificato in base alla relativa autorità emittente nel percorso di archivio predefinito (archivio locale del computer e archivio personale).</span><span class="sxs-lookup"><span data-stu-id="29d49-157">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="29d49-158">Aggiungere un [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) alla sezione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="29d49-158">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3. <span data-ttu-id="29d49-159">Aggiungere un elemento di associazione e quindi impostare l'attributo `name` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-159">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="29d49-160">Aggiungere un <`security`> e impostare il `mode` dell'attributo `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="29d49-160">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5. <span data-ttu-id="29d49-161">Aggiungere un <`message>` e impostare il `clientCredentialType` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-161">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="29d49-162">Per utilizzare l'associazione NetTcpBinding con Windows allo scopo di fornire la protezione a livello di trasporto</span><span class="sxs-lookup"><span data-stu-id="29d49-162">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1. <span data-ttu-id="29d49-163">Aggiungere un [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) alla sezione delle associazioni,</span><span class="sxs-lookup"><span data-stu-id="29d49-163">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2. <span data-ttu-id="29d49-164">Aggiungere un <`binding`> e impostare il `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-164">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="29d49-165">Aggiungere un <`security`> e impostare il `mode` dell'attributo `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="29d49-165">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4. <span data-ttu-id="29d49-166">Aggiungere un <`transport`> e impostare il `clientCredentialType` dell'attributo `Windows`.</span><span class="sxs-lookup"><span data-stu-id="29d49-166">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5. <span data-ttu-id="29d49-167">Aggiungere un <`message`> e impostare il `clientCredentialType` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="29d49-167">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="29d49-168">Nel codice seguente il valore viene impostato su un certificato.</span><span class="sxs-lookup"><span data-stu-id="29d49-168">The following code sets the value to a certificate.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="29d49-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29d49-169">See also</span></span>

- [<span data-ttu-id="29d49-170">Procedura: Impostare la modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="29d49-170">How to: Set the Security Mode</span></span>](../../../../docs/framework/wcf/how-to-set-the-security-mode.md)
- [<span data-ttu-id="29d49-171">Protezione dei servizi</span><span class="sxs-lookup"><span data-stu-id="29d49-171">Securing Services</span></span>](../../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="29d49-172">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="29d49-172">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
