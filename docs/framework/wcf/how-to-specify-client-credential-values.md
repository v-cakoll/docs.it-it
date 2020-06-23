---
title: 'Procedura: specificare valori di credenziali client'
description: Informazioni su come un servizio WCF può specificare il modo in cui un client viene autenticato per il servizio. Questo esempio specifica un certificato X. 509 e la modalità di trasporto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 75a21a7dc083282f6b2fe839167ff1b2eddfb373
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244452"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="6a27f-104">Procedura: specificare valori di credenziali client</span><span class="sxs-lookup"><span data-stu-id="6a27f-104">How to: Specify Client Credential Values</span></span>

<span data-ttu-id="6a27f-105">Utilizzando Windows Communication Foundation (WCF), il servizio può specificare il modo in cui un client viene autenticato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="6a27f-105">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="6a27f-106">Ad esempio, un servizio può stabilire che il client venga autenticato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="6a27f-106">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>

## <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="6a27f-107">Per determinare il tipo di credenziale client</span><span class="sxs-lookup"><span data-stu-id="6a27f-107">To determine the client credential type</span></span>

1. <span data-ttu-id="6a27f-108">Recuperare i metadati dall'endpoint dei metadati di servizio.</span><span class="sxs-lookup"><span data-stu-id="6a27f-108">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="6a27f-109">I metadati sono in genere costituiti da due file: il codice client del linguaggio di programmazione selezionato (l'impostazione predefinita è Visual C#) e un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="6a27f-109">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="6a27f-110">Un modo per recuperare i metadati consiste nell'utilizzare lo strumento Svcutil.exe per restituire il codice e la configurazione client.</span><span class="sxs-lookup"><span data-stu-id="6a27f-110">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="6a27f-111">Per ulteriori informazioni, vedere [recupero di metadati](./feature-details/retrieving-metadata.md) e [dello strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6a27f-111">For more information, see [Retrieving Metadata](./feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

2. <span data-ttu-id="6a27f-112">Aprire il file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="6a27f-112">Open the XML configuration file.</span></span> <span data-ttu-id="6a27f-113">Se si utilizza lo strumento Svcutil.exe, il nome predefinito del file è Output.config.</span><span class="sxs-lookup"><span data-stu-id="6a27f-113">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>

3. <span data-ttu-id="6a27f-114">Trovare l' **\<security>** elemento con l'attributo **mode** ( **\<security mode =**`MessageOrTransport`**>** dove `MessageOrTransport` è impostato su una delle modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6a27f-114">Find the **\<security>** element with the **mode** attribute (**\<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>

4. <span data-ttu-id="6a27f-115">Trovare l'elemento figlio che corrisponda al valore della modalità.</span><span class="sxs-lookup"><span data-stu-id="6a27f-115">Find the child element that matches the mode value.</span></span> <span data-ttu-id="6a27f-116">Ad esempio, se la modalità è impostata su **Message**, trovare l' **\<message>** elemento contenuto nell' **\<security>** elemento.</span><span class="sxs-lookup"><span data-stu-id="6a27f-116">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>

5. <span data-ttu-id="6a27f-117">Si noti il valore assegnato all'attributo **ClientCredentialType** .</span><span class="sxs-lookup"><span data-stu-id="6a27f-117">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="6a27f-118">Il valore effettivo dipende dalla modalità utilizzata, trasporto o messaggio.</span><span class="sxs-lookup"><span data-stu-id="6a27f-118">The actual value depends on which mode is used, transport or message.</span></span>

<span data-ttu-id="6a27f-119">Nel codice XML seguente viene mostrata la configurazione di un client per cui viene utilizzata la sicurezza dei messaggi e viene richiesto un certificato per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="6a27f-119">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="6a27f-120">Esempio: Modalità di trasporto TCP con certificato come credenziale client</span><span class="sxs-lookup"><span data-stu-id="6a27f-120">Example: TCP Transport Mode with Certificate as Client Credential</span></span>

<span data-ttu-id="6a27f-121">In questo esempio la modalità di sicurezza viene impostata sulla modalità Trasporto e il valore delle credenziali client su un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="6a27f-121">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="6a27f-122">Nelle procedure seguenti viene descritto come impostare il valore delle credenziali client sul client nel codice e nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="6a27f-122">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="6a27f-123">Si presuppone che sia stato utilizzato lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per restituire i metadati (codice e configurazione) dal servizio.</span><span class="sxs-lookup"><span data-stu-id="6a27f-123">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="6a27f-124">Per altre informazioni, vedere [How to: Create a client](how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="6a27f-124">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="6a27f-125">Per specificare il valore delle credenziali client nel client nel codice</span><span class="sxs-lookup"><span data-stu-id="6a27f-125">To specify the client credential value on the client in code</span></span>

1. <span data-ttu-id="6a27f-126">Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il codice e la configurazione dal servizio.</span><span class="sxs-lookup"><span data-stu-id="6a27f-126">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>

2. <span data-ttu-id="6a27f-127">Creare un'istanza del client WCF utilizzando il codice generato.</span><span class="sxs-lookup"><span data-stu-id="6a27f-127">Create an instance of the WCF client using the generated code.</span></span>

3. <span data-ttu-id="6a27f-128">Nella classe del client impostare la proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="6a27f-128">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="6a27f-129">In questo esempio la proprietà viene impostata su un certificato X.509 utilizzando il metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="6a27f-129">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     <span data-ttu-id="6a27f-130">È possibile utilizzare qualsiasi enumerazione della classe <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="6a27f-130">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="6a27f-131">Il nome del soggetto viene qui utilizzato nel caso in cui il certificato venga modificato (a causa di una data di scadenza).</span><span class="sxs-lookup"><span data-stu-id="6a27f-131">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="6a27f-132">L'utilizzo del nome del soggetto consente all'infrastruttura di cercare nuovamente il certificato.</span><span class="sxs-lookup"><span data-stu-id="6a27f-132">Using the subject name enables the infrastructure to find the certificate again.</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="6a27f-133">Per specificare il valore delle credenziali client nel client nella configurazione</span><span class="sxs-lookup"><span data-stu-id="6a27f-133">To specify the client credential value on the client in configuration</span></span>

1. <span data-ttu-id="6a27f-134">Aggiungere un [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento all' [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6a27f-134">Add a [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

2. <span data-ttu-id="6a27f-135">Aggiungere un [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) elemento all' [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6a27f-135">Add a [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="6a27f-136">Avere cura di impostare l'attributo `name` obbligatorio su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="6a27f-136">Be sure to set the required `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="6a27f-137">Aggiungere un [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) elemento all' [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6a27f-137">Add a [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>

4. <span data-ttu-id="6a27f-138">Impostare gli attributi seguenti sui valori appropriati: `storeLocation`, `storeName`, `x509FindType` e `findValue`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6a27f-138">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="6a27f-139">Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](./feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6a27f-139">For more information about certificates, see [Working with Certificates](./feature-details/working-with-certificates.md).</span></span>

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

5. <span data-ttu-id="6a27f-140">Quando si configura il client, specificare il comportamento impostando l'attributo `behaviorConfiguration` dell'elemento `<endpoint>`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6a27f-140">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="6a27f-141">L'elemento endpoint è figlio dell' [\<client>](../configure-apps/file-schema/wcf/client.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6a27f-141">The endpoint element is a child of the [\<client>](../configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="6a27f-142">Specificare inoltre il nome della configurazione dell'associazione impostando l'attributo `bindingConfiguration` sull'associazione per il client.</span><span class="sxs-lookup"><span data-stu-id="6a27f-142">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="6a27f-143">Se si utilizza un file di configurazione generato, il nome dell'associazione viene generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6a27f-143">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="6a27f-144">In questo esempio il nome è `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="6a27f-144">In this example, the name is `"tcpBindingWithCredential"`.</span></span>

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a><span data-ttu-id="6a27f-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a27f-145">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="6a27f-146">Programmazione delle funzionalità di sicurezza di WCF</span><span class="sxs-lookup"><span data-stu-id="6a27f-146">Programming WCF Security</span></span>](./feature-details/programming-wcf-security.md)
- [<span data-ttu-id="6a27f-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="6a27f-147">Selecting a Credential Type</span></span>](./feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="6a27f-148">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="6a27f-148">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="6a27f-149">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="6a27f-149">Working with Certificates</span></span>](./feature-details/working-with-certificates.md)
- [<span data-ttu-id="6a27f-150">Procedura: Creare un client</span><span class="sxs-lookup"><span data-stu-id="6a27f-150">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [\<message>](../configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
- [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md)
