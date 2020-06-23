---
title: 'Procedura: usare le funzionalità di sicurezza a livello di trasporto e le credenziali a livello di messaggio'
description: Viene illustrato come implementare la sicurezza del trasporto con le credenziali del messaggio, che offre il meglio delle modalità di sicurezza del trasporto e dei messaggi in WCF.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
ms.openlocfilehash: f632a4389eafc155cedcae94707c9418b6696f2c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246649"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="d3e24-103">Procedura: usare le funzionalità di sicurezza a livello di trasporto e le credenziali a livello di messaggio</span><span class="sxs-lookup"><span data-stu-id="d3e24-103">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="d3e24-104">La protezione di un servizio con credenziali di trasporto e di messaggio utilizza il meglio delle modalità di sicurezza del trasporto e dei messaggi in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d3e24-104">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="d3e24-105">Complessivamente, le funzionalità di sicurezza a livello di trasporto garantiscono integrità e riservatezza, mentre le funzionalità di sicurezza a livello di messaggio offrono vari tipi di credenziali non disponibili quando si utilizzano meccanismi di sicurezza basati esclusivamente sul livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d3e24-105">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="d3e24-106">In questo argomento vengono illustrati i passaggi di base per implementare il trasporto con credenziali messaggio utilizzando le associazioni <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-106">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> <span data-ttu-id="d3e24-107">Per altre informazioni sull'impostazione della modalità di sicurezza, vedere [procedura: impostare la modalità di sicurezza](../how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="d3e24-107">For more information about setting the security mode, see [How to: Set the Security Mode](../how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="d3e24-108">Quando si imposta la modalità di sicurezza su `TransportWithMessageCredential`, il trasporto determina il meccanismo di sicurezza a livello di trasporto effettivamente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-108">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="d3e24-109">Nel caso del protocollo HTTP, il meccanismo è Secure Sockets Layer (SSL) su HTTP (HTTPS). Nel caso del protocollo TCP, invece, il meccanismo è SSL su TCP oppure Windows.</span><span class="sxs-lookup"><span data-stu-id="d3e24-109">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="d3e24-110">Se il trasporto è HTTP (tramite l'associazione <xref:System.ServiceModel.WSHttpBinding>), il protocollo HTTPS fornisce la protezione a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d3e24-110">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="d3e24-111">In tal caso è necessario configurare il computer che ospita il servizio con un certificato SSL associato a una porta, come mostrato in seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d3e24-111">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="d3e24-112">Se il trasporto è TCP (tramite l'associazione <xref:System.ServiceModel.NetTcpBinding>), per impostazione predefinita la protezione a livello di trasporto fornita è la protezione di Windows oppure SSL su TCP.</span><span class="sxs-lookup"><span data-stu-id="d3e24-112">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="d3e24-113">Quando si utilizza SSL su TCP è necessario utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> per specificare il certificato, come mostrato in seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d3e24-113">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="d3e24-114">Per utilizzare l'associazione WSHttpBinding con un certificato allo scopo di fornire la protezione a livello di trasporto (in codice)</span><span class="sxs-lookup"><span data-stu-id="d3e24-114">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="d3e24-115">Usare lo strumento HttpCfg.exe per associare un certificato SSL a una porta del computer.</span><span class="sxs-lookup"><span data-stu-id="d3e24-115">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> <span data-ttu-id="d3e24-116">Per altre informazioni, vedere [procedura: configurare una porta con un certificato SSL](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="d3e24-116">For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2. <span data-ttu-id="d3e24-117">Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostare la proprietà <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> su <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-117">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3. <span data-ttu-id="d3e24-118">Impostare la proprietà <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-118">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="d3e24-119">Per ulteriori informazioni, vedere [selezione di un tipo di credenziale](selecting-a-credential-type.md). Il codice seguente usa il <xref:System.ServiceModel.MessageCredentialType.Certificate> valore.</span><span class="sxs-lookup"><span data-stu-id="d3e24-119">(For more information, see [Selecting a Credential Type](selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="d3e24-120">Creare un'istanza della classe <xref:System.Uri> con un indirizzo di base appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-120">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="d3e24-121">Si noti che l'indirizzo deve utilizzare lo schema "HTTPS" e deve contenere il nome effettivo del computer e il numero della porta a cui il certificato SSL è associato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-121">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="d3e24-122">In alternativa è possibile impostare l'indirizzo di base in configurazione.</span><span class="sxs-lookup"><span data-stu-id="d3e24-122">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="d3e24-123">Aggiungere un endpoint di servizio tramite il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-123">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6. <span data-ttu-id="d3e24-124">Creare l'istanza della classe <xref:System.ServiceModel.ServiceHost> e chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d3e24-124">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="d3e24-125">Per utilizzare l'associazione NetTcpBinding con un certificato allo scopo di fornire la protezione a livello di trasporto (in codice)</span><span class="sxs-lookup"><span data-stu-id="d3e24-125">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="d3e24-126">Creare un'istanza della classe <xref:System.ServiceModel.NetTcpBinding> e impostare la proprietà <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> su <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-126">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="d3e24-127">Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-127">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="d3e24-128">Nel codice seguente viene utilizzato il valore <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-128">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3. <span data-ttu-id="d3e24-129">Creare un'istanza della classe <xref:System.Uri> con un indirizzo di base appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-129">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="d3e24-130">Si noti che l'indirizzo deve utilizzare lo schema "net.tcp".</span><span class="sxs-lookup"><span data-stu-id="d3e24-130">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="d3e24-131">In alternativa è possibile impostare l'indirizzo di base in configurazione.</span><span class="sxs-lookup"><span data-stu-id="d3e24-131">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4. <span data-ttu-id="d3e24-132">Creare l'istanza della classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-132">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5. <span data-ttu-id="d3e24-133">Utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> per impostare in modo esplicito il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="d3e24-133">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6. <span data-ttu-id="d3e24-134">Aggiungere un endpoint di servizio tramite il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-134">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7. <span data-ttu-id="d3e24-135">Chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d3e24-135">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="d3e24-136">Per utilizzare l'associazione NetTcpBinding con Windows allo scopo di fornire la protezione a livello di trasporto (in codice)</span><span class="sxs-lookup"><span data-stu-id="d3e24-136">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1. <span data-ttu-id="d3e24-137">Creare un'istanza della classe <xref:System.ServiceModel.NetTcpBinding> e impostare la proprietà <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> su <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-137">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="d3e24-138">Impostare la protezione a livello di trasporto in modo che utilizzi Windows. A tale scopo, impostare la proprietà <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> su <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-138">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="d3e24-139">Si noti che questo valore è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d3e24-139">(Note that this is the default.)</span></span>  
  
3. <span data-ttu-id="d3e24-140">Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-140">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="d3e24-141">Nel codice seguente viene utilizzato il valore <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-141">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="d3e24-142">Creare un'istanza della classe <xref:System.Uri> con un indirizzo di base appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-142">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="d3e24-143">Si noti che l'indirizzo deve utilizzare lo schema "net.tcp".</span><span class="sxs-lookup"><span data-stu-id="d3e24-143">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="d3e24-144">In alternativa è possibile impostare l'indirizzo di base in configurazione.</span><span class="sxs-lookup"><span data-stu-id="d3e24-144">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="d3e24-145">Creare l'istanza della classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-145">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6. <span data-ttu-id="d3e24-146">Utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> per impostare in modo esplicito il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="d3e24-146">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7. <span data-ttu-id="d3e24-147">Aggiungere un endpoint di servizio tramite il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e24-147">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8. <span data-ttu-id="d3e24-148">Chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d3e24-148">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="d3e24-149">Utilizzo della configurazione</span><span class="sxs-lookup"><span data-stu-id="d3e24-149">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="d3e24-150">Per utilizzare l'associazione WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d3e24-150">To use the WSHttpBinding</span></span>  
  
1. <span data-ttu-id="d3e24-151">Configurare il computer con un certificato SSL associato a una porta.</span><span class="sxs-lookup"><span data-stu-id="d3e24-151">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="d3e24-152">Per altre informazioni, vedere [procedura: configurare una porta con un certificato SSL](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="d3e24-152">(For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="d3e24-153">Non è necessario impostare un <`transport`> valore dell'elemento con questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="d3e24-153">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2. <span data-ttu-id="d3e24-154">Specificare il tipo di credenziale client della protezione a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3e24-154">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="d3e24-155">Nell'esempio seguente viene impostato l' `clientCredentialType` attributo dell' `message` elemento <> su `UserName` .</span><span class="sxs-lookup"><span data-stu-id="d3e24-155">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="d3e24-156">Per utilizzare l'associazione NetTcpBinding con un certificato allo scopo di fornire la protezione a livello di trasporto</span><span class="sxs-lookup"><span data-stu-id="d3e24-156">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1. <span data-ttu-id="d3e24-157">Nel caso di SSL su TCP occorre specificare in modo esplicito il certificato nell'elemento `<behaviors>`.</span><span class="sxs-lookup"><span data-stu-id="d3e24-157">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="d3e24-158">Nell'esempio seguente viene individuato un certificato in base alla relativa autorità emittente nel percorso di archivio predefinito (archivio locale del computer e archivio personale).</span><span class="sxs-lookup"><span data-stu-id="d3e24-158">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
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
  
2. <span data-ttu-id="d3e24-159">Aggiungere un [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) alla sezione bindings</span><span class="sxs-lookup"><span data-stu-id="d3e24-159">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3. <span data-ttu-id="d3e24-160">Aggiungere un elemento di associazione e quindi impostare l'attributo `name` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-160">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="d3e24-161">Aggiungere un `security` elemento <> e impostare l' `mode` attributo su `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="d3e24-161">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5. <span data-ttu-id="d3e24-162">Aggiungere un `message>` elemento <e impostare l' `clientCredentialType` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-162">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
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
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="d3e24-163">Per utilizzare l'associazione NetTcpBinding con Windows allo scopo di fornire la protezione a livello di trasporto</span><span class="sxs-lookup"><span data-stu-id="d3e24-163">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1. <span data-ttu-id="d3e24-164">Aggiungere un [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) alla sezione bindings,</span><span class="sxs-lookup"><span data-stu-id="d3e24-164">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2. <span data-ttu-id="d3e24-165">Aggiungere un `binding` elemento <> e impostare l' `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-165">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="d3e24-166">Aggiungere un `security` elemento <> e impostare l' `mode` attributo su `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="d3e24-166">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4. <span data-ttu-id="d3e24-167">Aggiungere un `transport` elemento <> e impostare l' `clientCredentialType` attributo su `Windows` .</span><span class="sxs-lookup"><span data-stu-id="d3e24-167">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5. <span data-ttu-id="d3e24-168">Aggiungere un `message` elemento <> e impostare l' `clientCredentialType` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-168">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="d3e24-169">Nel codice seguente il valore viene impostato su un certificato.</span><span class="sxs-lookup"><span data-stu-id="d3e24-169">The following code sets the value to a certificate.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d3e24-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3e24-170">See also</span></span>

- [<span data-ttu-id="d3e24-171">Procedura: Impostare la modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d3e24-171">How to: Set the Security Mode</span></span>](../how-to-set-the-security-mode.md)
- [<span data-ttu-id="d3e24-172">Protezione dei servizi</span><span class="sxs-lookup"><span data-stu-id="d3e24-172">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="d3e24-173">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="d3e24-173">Securing Services and Clients</span></span>](securing-services-and-clients.md)
