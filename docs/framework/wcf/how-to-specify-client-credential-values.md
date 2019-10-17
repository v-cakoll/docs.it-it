---
title: 'Procedura: specificare valori di credenziali client'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 2417c2dd16224d6cbf00d3f1f4a8958420830b6c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319854"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="b41ab-102">Procedura: specificare valori di credenziali client</span><span class="sxs-lookup"><span data-stu-id="b41ab-102">How to: Specify Client Credential Values</span></span>

<span data-ttu-id="b41ab-103">Utilizzando Windows Communication Foundation (WCF), il servizio può specificare il modo in cui un client viene autenticato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="b41ab-103">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="b41ab-104">Ad esempio, un servizio può stabilire che il client venga autenticato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="b41ab-104">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>

## <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="b41ab-105">Per determinare il tipo di credenziale client</span><span class="sxs-lookup"><span data-stu-id="b41ab-105">To determine the client credential type</span></span>

1. <span data-ttu-id="b41ab-106">Recuperare i metadati dall'endpoint dei metadati di servizio.</span><span class="sxs-lookup"><span data-stu-id="b41ab-106">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="b41ab-107">I metadati sono in genere costituiti da due file: il codice client del linguaggio di programmazione selezionato (l'impostazione predefinita è Visual C#) e un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="b41ab-107">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="b41ab-108">Un modo per recuperare i metadati consiste nell'utilizzare lo strumento Svcutil.exe per restituire il codice e la configurazione client.</span><span class="sxs-lookup"><span data-stu-id="b41ab-108">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="b41ab-109">Per ulteriori informazioni, vedere [recupero di metadati](./feature-details/retrieving-metadata.md) e [ServiceModel Metadata Utility Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b41ab-109">For more information, see [Retrieving Metadata](./feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

2. <span data-ttu-id="b41ab-110">Aprire il file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="b41ab-110">Open the XML configuration file.</span></span> <span data-ttu-id="b41ab-111">Se si utilizza lo strumento Svcutil.exe, il nome predefinito del file è Output.config.</span><span class="sxs-lookup"><span data-stu-id="b41ab-111">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>

3. <span data-ttu-id="b41ab-112">Trovare l'elemento **\<security >** con l'attributo **mode** ( **\<security mode =** `MessageOrTransport` **>** dove `MessageOrTransport` è impostato su una delle modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b41ab-112">Find the **\<security>** element with the **mode** attribute (**\<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>

4. <span data-ttu-id="b41ab-113">Trovare l'elemento figlio che corrisponda al valore della modalità.</span><span class="sxs-lookup"><span data-stu-id="b41ab-113">Find the child element that matches the mode value.</span></span> <span data-ttu-id="b41ab-114">Se, ad esempio, la modalità è impostata su **Message**, trovare il **\<message elemento >** contenuto nell'elemento **\<security >** .</span><span class="sxs-lookup"><span data-stu-id="b41ab-114">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>

5. <span data-ttu-id="b41ab-115">Si noti il valore assegnato all'attributo **ClientCredentialType** .</span><span class="sxs-lookup"><span data-stu-id="b41ab-115">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="b41ab-116">Il valore effettivo dipende dalla modalità utilizzata, trasporto o messaggio.</span><span class="sxs-lookup"><span data-stu-id="b41ab-116">The actual value depends on which mode is used, transport or message.</span></span>

<span data-ttu-id="b41ab-117">Nel codice XML seguente viene mostrata la configurazione di un client per cui viene utilizzata la sicurezza dei messaggi e viene richiesto un certificato per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="b41ab-117">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="b41ab-118">Esempio: Modalità di trasporto TCP con certificato come credenziale client</span><span class="sxs-lookup"><span data-stu-id="b41ab-118">Example: TCP Transport Mode with Certificate as Client Credential</span></span>

<span data-ttu-id="b41ab-119">In questo esempio la modalità di sicurezza viene impostata sulla modalità Trasporto e il valore delle credenziali client su un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="b41ab-119">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="b41ab-120">Nelle procedure seguenti viene descritto come impostare il valore delle credenziali client sul client nel codice e nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="b41ab-120">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="b41ab-121">Si presuppone che sia stato utilizzato lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per restituire i metadati (codice e configurazione) dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b41ab-121">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="b41ab-122">Per altre informazioni, vedere [How to: Create a client](how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="b41ab-122">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="b41ab-123">Per specificare il valore delle credenziali client nel client nel codice</span><span class="sxs-lookup"><span data-stu-id="b41ab-123">To specify the client credential value on the client in code</span></span>

1. <span data-ttu-id="b41ab-124">Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il codice e la configurazione dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b41ab-124">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>

2. <span data-ttu-id="b41ab-125">Creare un'istanza del client WCF utilizzando il codice generato.</span><span class="sxs-lookup"><span data-stu-id="b41ab-125">Create an instance of the WCF client using the generated code.</span></span>

3. <span data-ttu-id="b41ab-126">Nella classe del client impostare la proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="b41ab-126">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="b41ab-127">In questo esempio la proprietà viene impostata su un certificato X.509 utilizzando il metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="b41ab-127">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     <span data-ttu-id="b41ab-128">È possibile utilizzare qualsiasi enumerazione della classe <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="b41ab-128">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="b41ab-129">Il nome del soggetto viene qui utilizzato nel caso in cui il certificato venga modificato (a causa di una data di scadenza).</span><span class="sxs-lookup"><span data-stu-id="b41ab-129">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="b41ab-130">L'utilizzo del nome del soggetto consente all'infrastruttura di cercare nuovamente il certificato.</span><span class="sxs-lookup"><span data-stu-id="b41ab-130">Using the subject name enables the infrastructure to find the certificate again.</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="b41ab-131">Per specificare il valore delle credenziali client nel client nella configurazione</span><span class="sxs-lookup"><span data-stu-id="b41ab-131">To specify the client credential value on the client in configuration</span></span>

1. <span data-ttu-id="b41ab-132">Aggiungere un elemento [\<behavior >](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) all'elemento [\<behaviors >](../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="b41ab-132">Add a [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

2. <span data-ttu-id="b41ab-133">Aggiungere un elemento [\<clientCredentials >](../configure-apps/file-schema/wcf/clientcredentials.md) all'elemento [\<behaviors >](../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="b41ab-133">Add a [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="b41ab-134">Avere cura di impostare l'attributo `name` obbligatorio su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="b41ab-134">Be sure to set the required `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="b41ab-135">Aggiungere un elemento [\<clientCertificate >](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) all'elemento [\<clientCredentials >](../configure-apps/file-schema/wcf/clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="b41ab-135">Add a [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>

4. <span data-ttu-id="b41ab-136">Impostare gli attributi seguenti sui valori appropriati: `storeLocation`, `storeName`, `x509FindType` e `findValue`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b41ab-136">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="b41ab-137">Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](./feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="b41ab-137">For more information about certificates, see [Working with Certificates](./feature-details/working-with-certificates.md).</span></span>

    ```xml
    <behaviors>
       <endpointBehaviors>
          <behavior name="endpointCredentialBehavior">
            <clientCredentials>
              <clientCertificate findValue="Contoso.com"
                                 storeLocation="LocalMachine"
                                 storeName="TrustedPeople"
                                 x509FindType="FindBySubjectName" />
            </clientCredentials>
          </behavior>
       </endpointBehaviors>
    </behaviors>
    ```

5. <span data-ttu-id="b41ab-138">Quando si configura il client, specificare il comportamento impostando l'attributo `behaviorConfiguration` dell'elemento `<endpoint>`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b41ab-138">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="b41ab-139">L'elemento endpoint è figlio dell'elemento [\<client >](../configure-apps/file-schema/wcf/client.md) .</span><span class="sxs-lookup"><span data-stu-id="b41ab-139">The endpoint element is a child of the [\<client>](../configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="b41ab-140">Specificare inoltre il nome della configurazione dell'associazione impostando l'attributo `bindingConfiguration` sull'associazione per il client.</span><span class="sxs-lookup"><span data-stu-id="b41ab-140">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="b41ab-141">Se si utilizza un file di configurazione generato, il nome dell'associazione viene generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b41ab-141">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="b41ab-142">In questo esempio il nome è `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="b41ab-142">In this example, the name is `"tcpBindingWithCredential"`.</span></span>

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a><span data-ttu-id="b41ab-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b41ab-143">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="b41ab-144">Programmazione delle funzionalità di sicurezza di WCF</span><span class="sxs-lookup"><span data-stu-id="b41ab-144">Programming WCF Security</span></span>](./feature-details/programming-wcf-security.md)
- [<span data-ttu-id="b41ab-145">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="b41ab-145">Selecting a Credential Type</span></span>](./feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="b41ab-146">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="b41ab-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="b41ab-147">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="b41ab-147">Working with Certificates</span></span>](./feature-details/working-with-certificates.md)
- [<span data-ttu-id="b41ab-148">Procedura: Creare un client</span><span class="sxs-lookup"><span data-stu-id="b41ab-148">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="b41ab-149">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="b41ab-149">\<netTcpBinding></span></span>](../configure-apps/file-schema/wcf/nettcpbinding.md)
- [<span data-ttu-id="b41ab-150">\<security ></span><span class="sxs-lookup"><span data-stu-id="b41ab-150">\<security></span></span>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [<span data-ttu-id="b41ab-151">\<message ></span><span class="sxs-lookup"><span data-stu-id="b41ab-151">\<message></span></span>](../configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [<span data-ttu-id="b41ab-152">\<behavior ></span><span class="sxs-lookup"><span data-stu-id="b41ab-152">\<behavior></span></span>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [<span data-ttu-id="b41ab-153">\<behaviors ></span><span class="sxs-lookup"><span data-stu-id="b41ab-153">\<behaviors></span></span>](../configure-apps/file-schema/wcf/behaviors.md)
- [<span data-ttu-id="b41ab-154">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="b41ab-154">\<clientCertificate></span></span>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [<span data-ttu-id="b41ab-155">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="b41ab-155">\<clientCredentials></span></span>](../configure-apps/file-schema/wcf/clientcredentials.md)
