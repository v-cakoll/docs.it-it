---
title: 'Procedura: proteggere un servizio con credenziali di Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
author: BrucePerlerMS
ms.openlocfilehash: bf88073c25351aac0e421d69a947605de3e37759
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200698"
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a><span data-ttu-id="d46ac-102">Procedura: proteggere un servizio con credenziali di Windows</span><span class="sxs-lookup"><span data-stu-id="d46ac-102">How to: Secure a Service with Windows Credentials</span></span>
<span data-ttu-id="d46ac-103">Questo argomento illustra come abilitare la sicurezza del trasporto in un servizio Windows Communication Foundation (WCF) che risiede in un dominio di Windows e viene chiamato dai client nello stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-103">This topic shows how to enable transport security on a Windows Communication Foundation (WCF) service that resides in a Windows domain and is called by clients in the same domain.</span></span> <span data-ttu-id="d46ac-104">Per altre informazioni su questo scenario, vedere [protezione del trasporto con autenticazione di Windows](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d46ac-104">For more information about this scenario, see [Transport Security with Windows Authentication](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md).</span></span> <span data-ttu-id="d46ac-105">Per un'applicazione di esempio, vedere la [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-105">For a sample application, see the [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span>  
  
 <span data-ttu-id="d46ac-106">In questo argomento si presuppone la presenza di un'interfaccia e di un'implementazione del contratto esistente già definite, alle quali vengono aggiunti elementi.</span><span class="sxs-lookup"><span data-stu-id="d46ac-106">This topic assumes you have an existing contract interface and implementation already defined, and adds on to that.</span></span> <span data-ttu-id="d46ac-107">È inoltre possibile modificare un servizio e un client esistenti.</span><span class="sxs-lookup"><span data-stu-id="d46ac-107">You can also modify an existing service and client.</span></span>  
  
 <span data-ttu-id="d46ac-108">È possibile proteggere un servizio con credenziali di Windows completamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="d46ac-108">You can secure a service with Windows credentials completely in code.</span></span> <span data-ttu-id="d46ac-109">In alternativa, è possibile omettere parte del codice tramite un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d46ac-109">Alternatively, you can omit some of the code by using a configuration file.</span></span> <span data-ttu-id="d46ac-110">In questo argomento vengono illustrate entrambe le modalità.</span><span class="sxs-lookup"><span data-stu-id="d46ac-110">This topic shows both ways.</span></span> <span data-ttu-id="d46ac-111">Accertarsi di usare una sola modalità, non entrambe.</span><span class="sxs-lookup"><span data-stu-id="d46ac-111">Be sure you only use one of the ways, not both.</span></span>  
  
 <span data-ttu-id="d46ac-112">Nelle prime tre procedure viene illustrato come proteggere il servizio tramite il codice.</span><span class="sxs-lookup"><span data-stu-id="d46ac-112">The first three procedures show how to secure the service using code.</span></span> <span data-ttu-id="d46ac-113">Nella quarta e nella quinta procedura viene illustrato come eseguire questa operazione con un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d46ac-113">The fourth and fifth procedure shows how to do it with a configuration file.</span></span>  
  
## <a name="using-code"></a><span data-ttu-id="d46ac-114">Uso del codice</span><span class="sxs-lookup"><span data-stu-id="d46ac-114">Using Code</span></span>  
 <span data-ttu-id="d46ac-115">Il codice completo per il servizio e il client si trova nella sezione Esempio alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d46ac-115">The complete code for the service and the client is in the Example section at the end of this topic.</span></span>  
  
 <span data-ttu-id="d46ac-116">Nella prima procedura vengono illustrate la creazione e la configurazione di una classe <xref:System.ServiceModel.WSHttpBinding> nel codice.</span><span class="sxs-lookup"><span data-stu-id="d46ac-116">The first procedure walks through creating and configuring a <xref:System.ServiceModel.WSHttpBinding> class in code.</span></span> <span data-ttu-id="d46ac-117">Per l'associazione viene usata il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="d46ac-117">The binding uses the HTTP transport.</span></span> <span data-ttu-id="d46ac-118">La stessa associazione viene usata nel client.</span><span class="sxs-lookup"><span data-stu-id="d46ac-118">The same binding is used on the client.</span></span>  
  
#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a><span data-ttu-id="d46ac-119">Per creare un oggetto WSHttpBinding che usa le credenziali di Windows e la protezione dei messaggio</span><span class="sxs-lookup"><span data-stu-id="d46ac-119">To create a WSHttpBinding that uses Windows credentials and message security</span></span>  
  
1.  <span data-ttu-id="d46ac-120">Il codice di questa procedura viene inserito all'inizio del metodo `Run` della classe `Test` nel codice del servizio riportato nella sezione Esempio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-120">This procedure's code is inserted at the beginning of the `Run` method of the `Test` class in the service code in the Example section.</span></span>  
  
2.  <span data-ttu-id="d46ac-121">Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="d46ac-121">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
3.  <span data-ttu-id="d46ac-122">Impostare la proprietà <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> della classe <xref:System.ServiceModel.WSHttpSecurity> su <xref:System.ServiceModel.SecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="d46ac-122">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property of the <xref:System.ServiceModel.WSHttpSecurity> class to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>  
  
4.  <span data-ttu-id="d46ac-123">Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> della classe <xref:System.ServiceModel.MessageSecurityOverHttp> su <xref:System.ServiceModel.MessageCredentialType.Windows>.</span><span class="sxs-lookup"><span data-stu-id="d46ac-123">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property of the <xref:System.ServiceModel.MessageSecurityOverHttp> class to <xref:System.ServiceModel.MessageCredentialType.Windows>.</span></span>  
  
5.  <span data-ttu-id="d46ac-124">Il codice per questa procedura è il seguente:</span><span class="sxs-lookup"><span data-stu-id="d46ac-124">The code for this procedure is as follows:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
     [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]  
  
### <a name="using-the-binding-in-a-service"></a><span data-ttu-id="d46ac-125">Uso dell'associazione in un servizio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-125">Using the Binding in a Service</span></span>  
 <span data-ttu-id="d46ac-126">Si tratta della seconda procedura, in cui viene illustrato l'uso dell'associazione in un servizio self-hosted.</span><span class="sxs-lookup"><span data-stu-id="d46ac-126">This is the second procedure, which shows how to use the binding in a self-hosted service.</span></span> <span data-ttu-id="d46ac-127">Per altre informazioni sui servizi di hosting vedere [servizi di Hosting](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="d46ac-127">For more information about hosting services see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
##### <a name="to-use-a-binding-in-a-service"></a><span data-ttu-id="d46ac-128">Per usare un'associazione in un servizio</span><span class="sxs-lookup"><span data-stu-id="d46ac-128">To use a binding in a service</span></span>  
  
1.  <span data-ttu-id="d46ac-129">Inserire il codice di questa procedura dopo il codice della procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="d46ac-129">Insert this procedure's code after the code from the preceding procedure.</span></span>  
  
2.  <span data-ttu-id="d46ac-130">Creare una variabile <xref:System.Type> denominata `contractType` e assegnarle il tipo dell'interfaccia (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="d46ac-130">Create a <xref:System.Type> variable named `contractType` and assign it the type of the interface (`ICalculator`).</span></span> <span data-ttu-id="d46ac-131">Quando si usa Visual Basic, usare il `GetType` operatore; quando si usa c#, usare il `typeof` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="d46ac-131">When using Visual Basic, use the `GetType` operator; when using C#, use the `typeof` keyword.</span></span>  
  
3.  <span data-ttu-id="d46ac-132">Creare una seconda variabile `Type` denominata `serviceType` e assegnarle il tipo del contratto implementato (`Calculator`).</span><span class="sxs-lookup"><span data-stu-id="d46ac-132">Create a second `Type` variable named `serviceType` and assign it the type of the implemented contract (`Calculator`).</span></span>  
  
4.  <span data-ttu-id="d46ac-133">Creare un'istanza della classe <xref:System.Uri> denominata `baseAddress` con l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-133">Create an instance of the <xref:System.Uri> class named `baseAddress` with the base address of the service.</span></span> <span data-ttu-id="d46ac-134">L'indirizzo di base deve avere uno schema corrispondente al trasporto.</span><span class="sxs-lookup"><span data-stu-id="d46ac-134">The base address must have a scheme that matches the transport.</span></span> <span data-ttu-id="d46ac-135">In questo caso, lo schema di trasporto è HTTP e l'indirizzo include il particolare Uniform Resource Identifier (URI) "localhost" e una porta (8036) il numero e un indirizzo di base dell'endpoint ("serviceModelSamples /): http://localhost:8036/serviceModelSamples/.</span><span class="sxs-lookup"><span data-stu-id="d46ac-135">In this case, the transport scheme is HTTP, and the address includes the special Uniform Resource Identifier (URI) "localhost" and a port number (8036) as well as a base endpoint address ("serviceModelSamples/): http://localhost:8036/serviceModelSamples/.</span></span>  
  
5.  <span data-ttu-id="d46ac-136">Creare un'istanza della classe <xref:System.ServiceModel.ServiceHost> class con le variabili `serviceType` e `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="d46ac-136">Create an instance of the <xref:System.ServiceModel.ServiceHost> class with the `serviceType` and `baseAddress` variables.</span></span>  
  
6.  <span data-ttu-id="d46ac-137">Aggiungere un endpoint al servizio tramite l'interfaccia `contractType`, l'associazione e un nome di endpoint (secureCalculator).</span><span class="sxs-lookup"><span data-stu-id="d46ac-137">Add an endpoint to the service using the `contractType`, binding, and an endpoint name (secureCalculator).</span></span> <span data-ttu-id="d46ac-138">Un client deve concatenare l'indirizzo di base e il nome dell'endpoint quando avvia una chiamata al servizio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-138">A client must concatenate the base address and the endpoint name when initiating a call to the service.</span></span>  
  
7.  <span data-ttu-id="d46ac-139">Chiamare il metodo <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-139">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service.</span></span> <span data-ttu-id="d46ac-140">Il codice per questa procedura viene illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d46ac-140">The code for this procedure is shown here:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
     [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="d46ac-141">Uso dell'associazione in un client</span><span class="sxs-lookup"><span data-stu-id="d46ac-141">Using the Binding in a Client</span></span>  
 <span data-ttu-id="d46ac-142">In questa procedura viene illustrato come generare un proxy che comunica con il servizio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-142">This procedure shows how to generate a proxy that communicates with the service.</span></span> <span data-ttu-id="d46ac-143">Il proxy viene generato con il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) che usa i metadati del servizio per creare il proxy.</span><span class="sxs-lookup"><span data-stu-id="d46ac-143">The proxy is generated with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) which uses the service metadata to create the proxy.</span></span>  
  
 <span data-ttu-id="d46ac-144">In questa procedura viene anche creata un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> per comunicare con il servizio, quindi viene chiamato il servizio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-144">This procedure also creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class to communicate with the service, and then calls the service.</span></span>  
  
 <span data-ttu-id="d46ac-145">In questo esempio, per creare il client viene usato solo codice.</span><span class="sxs-lookup"><span data-stu-id="d46ac-145">This example uses only code to create the client.</span></span> <span data-ttu-id="d46ac-146">In alternativa, è possibile usare un file di configurazione, illustrato nella sezione successiva a questa procedura.</span><span class="sxs-lookup"><span data-stu-id="d46ac-146">As an alternative, you can use a configuration file, which is shown in the section following this procedure.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-code"></a><span data-ttu-id="d46ac-147">Per usare un'associazione in un client con codice</span><span class="sxs-lookup"><span data-stu-id="d46ac-147">To use a binding in a client with code</span></span>  
  
1.  <span data-ttu-id="d46ac-148">Usare lo strumento SvcUtil.exe per generare il codice del proxy tramite i metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-148">Use the SvcUtil.exe tool to generate the proxy code from the service's metadata.</span></span> <span data-ttu-id="d46ac-149">Per altre informazioni, vedere [procedura: creare un Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="d46ac-149">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="d46ac-150">Il codice proxy generato eredita il <xref:System.ServiceModel.ClientBase%601> (classe), che assicura che ogni client disponga di costruttori necessari, i metodi e proprietà per comunicare con un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="d46ac-150">The generated proxy code inherits from the <xref:System.ServiceModel.ClientBase%601> class, which ensures that every client has the necessary constructors, methods, and properties to communicate with a WCF service.</span></span> <span data-ttu-id="d46ac-151">In questo esempio, il codice generato include la classe `CalculatorClient` che implementa l'interfaccia `ICalculator`, consentendo la compatibilità con il codice del servizio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-151">In this example, the generated code includes the `CalculatorClient` class, which implements the `ICalculator` interface, enabling compatibility with the service code.</span></span>  
  
2.  <span data-ttu-id="d46ac-152">Il codice di questa procedura viene inserito all'inizio del metodo `Main` del programma client.</span><span class="sxs-lookup"><span data-stu-id="d46ac-152">This procedure's code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
3.  <span data-ttu-id="d46ac-153">Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostarne la modalità di sicurezza su `Message` e il tipo di credenziale client su `Windows`.</span><span class="sxs-lookup"><span data-stu-id="d46ac-153">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to `Message` and its client credential type to `Windows`.</span></span> <span data-ttu-id="d46ac-154">Nell'esempio viene denominata la variabile `clientBinding`.</span><span class="sxs-lookup"><span data-stu-id="d46ac-154">The example names the variable `clientBinding`.</span></span>  
  
4.  <span data-ttu-id="d46ac-155">Creare un'istanza della classe <xref:System.ServiceModel.EndpointAddress> denominata `serviceAddress`.</span><span class="sxs-lookup"><span data-stu-id="d46ac-155">Create an instance of the <xref:System.ServiceModel.EndpointAddress> class named `serviceAddress`.</span></span> <span data-ttu-id="d46ac-156">Inizializzare l'istanza con l'indirizzo di base concatenato al nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d46ac-156">Initialize the instance with the base address concatenated with the endpoint name.</span></span>  
  
5.  <span data-ttu-id="d46ac-157">Creare un'istanza della classe client generata con le variabili `serviceAddress` e `clientBinding`.</span><span class="sxs-lookup"><span data-stu-id="d46ac-157">Create an instance of the generated client class with the `serviceAddress` and the `clientBinding` variables.</span></span>  
  
6.  <span data-ttu-id="d46ac-158">Chiamare il metodo <xref:System.ServiceModel.ClientBase%601.Open%2A>, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d46ac-158">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
7.  <span data-ttu-id="d46ac-159">Chiamare il servizio e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="d46ac-159">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
     [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]  
  
## <a name="using-the-configuration-file"></a><span data-ttu-id="d46ac-160">Uso del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d46ac-160">Using the Configuration File</span></span>  
 <span data-ttu-id="d46ac-161">Anziché creare l'associazione con codice procedurale, è possibile usare il codice seguente illustrato per la sezione dell'associazione del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d46ac-161">Instead of creating the binding with procedural code, you can use the following code shown for the bindings section of the configuration file.</span></span>  
  
 <span data-ttu-id="d46ac-162">Se si dispone già di un servizio definito, vedere [progettazione e implementazione di servizi](../../../docs/framework/wcf/designing-and-implementing-services.md), e [configurazione di servizi](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="d46ac-162">If you do not already have a service defined, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md), and [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
 <span data-ttu-id="d46ac-163">**Nota** questo codice di configurazione viene usato nei file di configurazione del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="d46ac-163">**Note** This configuration code is used in both the service and client configuration files.</span></span>  
  
#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a><span data-ttu-id="d46ac-164">Per abilitare la protezione del trasferimento in un servizio in un dominio Windows usando la configurazione</span><span class="sxs-lookup"><span data-stu-id="d46ac-164">To enable transfer security on a service in a Windows domain using configuration</span></span>  
  
1.  <span data-ttu-id="d46ac-165">Aggiungere un [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento per il [ \<associazioni >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) sezione dell'elemento del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d46ac-165">Add a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section of the configuration file.</span></span>  
  
2.  <span data-ttu-id="d46ac-166">Aggiungere un elemento <`binding`> all'elemento <`WSHttpBinding`> e impostare l'attributo `configurationName` su un valore appropriato per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d46ac-166">Add a <`binding`> element to the <`WSHttpBinding`> element and set the `configurationName` attribute to a value appropriate to your application.</span></span>  
  
3.  <span data-ttu-id="d46ac-167">Aggiungere un elemento <`security`> e impostare l'attributo `mode` su Message.</span><span class="sxs-lookup"><span data-stu-id="d46ac-167">Add a <`security`> element and set the `mode` attribute to Message.</span></span>  
  
4.  <span data-ttu-id="d46ac-168">Aggiungere un elemento <`message`> e impostare l'attributo `clientCredentialType` su Windows.</span><span class="sxs-lookup"><span data-stu-id="d46ac-168">Add a <`message`> element and set the `clientCredentialType` attribute to Windows.</span></span>  
  
5.  <span data-ttu-id="d46ac-169">Nel file di configurazione del servizio, sostituire la sezione `<bindings>` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d46ac-169">In the service's configuration file, replace the `<bindings>` section with the following code.</span></span> <span data-ttu-id="d46ac-170">Se si dispone già di un file di configurazione del servizio, vedere [utilizzando le associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d46ac-170">If you do not already have a service configuration file, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="d46ac-171">Uso dell'associazione in un client</span><span class="sxs-lookup"><span data-stu-id="d46ac-171">Using the Binding in a Client</span></span>  
 <span data-ttu-id="d46ac-172">In questa procedura viene illustrato come generare due file, un proxy che comunica con il servizio e un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d46ac-172">This procedure shows how to generate two files: a proxy that communicates with the service and a configuration file.</span></span> <span data-ttu-id="d46ac-173">Vengono inoltre descritte le modifiche apportate al programma client, ovvero il terzo file usato nel client.</span><span class="sxs-lookup"><span data-stu-id="d46ac-173">It also describes changes to the client program, which is the third file used on the client.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-configuration"></a><span data-ttu-id="d46ac-174">Per usare un'associazione in un client con configurazione</span><span class="sxs-lookup"><span data-stu-id="d46ac-174">To use a binding in a client with configuration</span></span>  
  
1.  <span data-ttu-id="d46ac-175">Usare lo strumento SvcUtil.exe per generare il codice proxy e il file di configurazione tramite i metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="d46ac-175">Use the SvcUtil.exe tool to generate the proxy code and configuration file from the service's metadata.</span></span> <span data-ttu-id="d46ac-176">Per altre informazioni, vedere [procedura: creare un Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="d46ac-176">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="d46ac-177">Sostituire il [ \<associazioni >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) sezione del file di configurazione generato con il codice di configurazione nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="d46ac-177">Replace the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) section of the generated configuration file with the configuration code from the preceding section.</span></span>  
  
3.  <span data-ttu-id="d46ac-178">Il codice procedurale viene inserito all'inizio del metodo `Main` del programma client.</span><span class="sxs-lookup"><span data-stu-id="d46ac-178">Procedural code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
4.  <span data-ttu-id="d46ac-179">Creare un'istanza della classe client generata che passi il nome dell'associazione nel file di configurazione come parametro di input.</span><span class="sxs-lookup"><span data-stu-id="d46ac-179">Create an instance of the generated client class passing the name of the binding in the configuration file as an input parameter.</span></span>  
  
5.  <span data-ttu-id="d46ac-180">Chiamare il metodo <xref:System.ServiceModel.ClientBase%601.Open%2A>, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d46ac-180">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
6.  <span data-ttu-id="d46ac-181">Chiamare il servizio e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="d46ac-181">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="d46ac-182">Esempio</span><span class="sxs-lookup"><span data-stu-id="d46ac-182">Example</span></span>  
 [!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]  
  
 [!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)] 
 [!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]      
  
## <a name="see-also"></a><span data-ttu-id="d46ac-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d46ac-183">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpBinding>  
 [<span data-ttu-id="d46ac-184">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="d46ac-184">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="d46ac-185">Procedura: Creare un client</span><span class="sxs-lookup"><span data-stu-id="d46ac-185">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="d46ac-186">Protezione dei servizi</span><span class="sxs-lookup"><span data-stu-id="d46ac-186">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="d46ac-187">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d46ac-187">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)
