---
title: 'Procedura: proteggere un servizio con un certificato X.509'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d06c2aa-d0d7-4e5e-ad7e-77416aa1c10b
ms.openlocfilehash: 10d6db63368ee55040f85f922b9483982e8ff264
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596968"
---
# <a name="how-to-secure-a-service-with-an-x509-certificate"></a><span data-ttu-id="db80e-102">Procedura: proteggere un servizio con un certificato X.509</span><span class="sxs-lookup"><span data-stu-id="db80e-102">How to: Secure a Service with an X.509 Certificate</span></span>
<span data-ttu-id="db80e-103">La protezione di un servizio con un certificato X. 509 è una tecnica di base utilizzata dalla maggior parte delle associazioni in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="db80e-103">Securing a service with an X.509 certificate is a basic technique that most bindings in Windows Communication Foundation (WCF) use.</span></span> <span data-ttu-id="db80e-104">In questo argomento vengono illustrati i passaggi di configurazione di un servizio indipendente con un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="db80e-104">This topic walks through the steps of configuring a self-hosted service with an X.509 certificate.</span></span>  
  
 <span data-ttu-id="db80e-105">Un prerequisito è un certificato valido utilizzabile per autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="db80e-105">A prerequisite is a valid certificate that can be used to authenticate the server.</span></span> <span data-ttu-id="db80e-106">Il certificato deve essere emesso al server da un autorità di certificazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="db80e-106">The certificate must be issued to the server by a trusted certificate authority.</span></span> <span data-ttu-id="db80e-107">Se il certificato non è valido, nessun client che tenti di utilizzare il servizio lo reputerà attendibile e, di conseguenza, non verrà stabilita nessuna connessione.</span><span class="sxs-lookup"><span data-stu-id="db80e-107">If the certificate is not valid, any client trying to use the service will not trust the service, and consequently no connection will be made.</span></span> <span data-ttu-id="db80e-108">Per ulteriori informazioni sull'utilizzo dei certificati, vedere [utilizzo dei certificati](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="db80e-108">For more information about using certificates, see [Working with Certificates](working-with-certificates.md).</span></span>  
  
### <a name="to-configure-a-service-with-a-certificate-using-code"></a><span data-ttu-id="db80e-109">Per configurare un servizio con un certificato utilizzando codice.</span><span class="sxs-lookup"><span data-stu-id="db80e-109">To configure a service with a certificate using code</span></span>  
  
1. <span data-ttu-id="db80e-110">Creare il contratto di servizio e il servizio implementato.</span><span class="sxs-lookup"><span data-stu-id="db80e-110">Create the service contract and the implemented service.</span></span> <span data-ttu-id="db80e-111">Per ulteriori informazioni, vedere [progettazione e implementazione di servizi](../designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="db80e-111">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md).</span></span>  
  
2. <span data-ttu-id="db80e-112">Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostarne la modalità sicura su <xref:System.ServiceModel.SecurityMode.Message>, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="db80e-112">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#1)]
     [!code-vb[C_SecureWithCertificate#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#1)]  
  
3. <span data-ttu-id="db80e-113">Creare due variabili <xref:System.Type>, una per il tipo di contratto e una per il contratto implementato, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="db80e-113">Create two <xref:System.Type> variables, one each for the contract type and the implemented contract, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#2)]
     [!code-vb[C_SecureWithCertificate#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#2)]  
  
4. <span data-ttu-id="db80e-114">Creare un'istanza della classe <xref:System.Uri> per l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="db80e-114">Create an instance of the <xref:System.Uri> class for the base address of the service.</span></span> <span data-ttu-id="db80e-115">Poiché `WSHttpBinding` utilizza il trasporto HTTP, il Uniform Resource Identifier (URI) deve iniziare con tale schema oppure Windows Communication Foundation (WCF) genererà un'eccezione quando il servizio viene aperto.</span><span class="sxs-lookup"><span data-stu-id="db80e-115">Because the `WSHttpBinding` uses the HTTP transport, the Uniform Resource Identifier (URI) must begin with that schema, or Windows Communication Foundation (WCF) will throw an exception when the service is opened.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#3)]
     [!code-vb[C_SecureWithCertificate#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#3)]  
  
5. <span data-ttu-id="db80e-116">Creare una nuova istanza della classe <xref:System.ServiceModel.ServiceHost> con la variabile del tipo di contratto implementato e l'URI.</span><span class="sxs-lookup"><span data-stu-id="db80e-116">Create a new instance of the <xref:System.ServiceModel.ServiceHost> class with the implemented contract type variable and the URI.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#4)]
     [!code-vb[C_SecureWithCertificate#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#4)]  
  
6. <span data-ttu-id="db80e-117">Aggiungere un <xref:System.ServiceModel.Description.ServiceEndpoint> al servizio utilizzando il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="db80e-117">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> to the service using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span> <span data-ttu-id="db80e-118">Passare il contratto, l'associazione e un indirizzo endpoint al costruttore, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="db80e-118">Pass the contract, binding, and an endpoint address to the constructor, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#5)]
     [!code-vb[C_SecureWithCertificate#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#5)]  
  
7. <span data-ttu-id="db80e-119">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="db80e-119">Optional.</span></span> <span data-ttu-id="db80e-120">Per recuperare metadati dal servizio, creare un nuovo oggetto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> e impostare la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="db80e-120">To retrieve metadata from the service, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> object and set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#6)]
     [!code-vb[C_SecureWithCertificate#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#6)]  
  
8. <span data-ttu-id="db80e-121">Utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> per aggiungere il certificato valido al servizio.</span><span class="sxs-lookup"><span data-stu-id="db80e-121">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to add the valid certificate to the service.</span></span> <span data-ttu-id="db80e-122">Il metodo può utilizzare uno di numerosi metodi per trovare un certificato.</span><span class="sxs-lookup"><span data-stu-id="db80e-122">The method can use one of several methods to find a certificate.</span></span> <span data-ttu-id="db80e-123">Nell'esempio viene utilizzata l'enumerazione <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName>.</span><span class="sxs-lookup"><span data-stu-id="db80e-123">This example uses the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> enumeration.</span></span> <span data-ttu-id="db80e-124">L'enumerazione specifica che il valore fornito è il nome dell'entità alla quale è stato emesso il certificato.</span><span class="sxs-lookup"><span data-stu-id="db80e-124">The enumeration specifies that the supplied value is the name of the entity that the certificate was issued to.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#7)]
     [!code-vb[C_SecureWithCertificate#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#7)]  
  
9. <span data-ttu-id="db80e-125">Chiamare il metodo <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> per avviare l'ascolto del servizio.</span><span class="sxs-lookup"><span data-stu-id="db80e-125">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service listening.</span></span> <span data-ttu-id="db80e-126">Se si sta creando un'applicazione console, chiamare il metodo <xref:System.Console.ReadLine%2A> per tenere il servizio nello stato di ascolto.</span><span class="sxs-lookup"><span data-stu-id="db80e-126">If you are creating a console application, call the <xref:System.Console.ReadLine%2A> method to keep the service in the listening state.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#8)]
     [!code-vb[C_SecureWithCertificate#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="db80e-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="db80e-127">Example</span></span>  
 <span data-ttu-id="db80e-128">Nell'esempio seguente viene utilizzato il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> per configurare un servizio con un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="db80e-128">The following example uses the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method to configure a service with an X.509 certificate.</span></span>  
  
 [!code-csharp[C_SecureWithCertificate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#9)]
 [!code-vb[C_SecureWithCertificate#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="db80e-129">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="db80e-129">Compiling the Code</span></span>  
 <span data-ttu-id="db80e-130">Per compilare il codice sono necessari gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="db80e-130">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.Web.Services.Description>  
  
- <xref:System.Security.Cryptography.X509Certificates>  
  
- <xref:System.Runtime.Serialization>  
  
## <a name="see-also"></a><span data-ttu-id="db80e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db80e-131">See also</span></span>

- [<span data-ttu-id="db80e-132">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="db80e-132">Working with Certificates</span></span>](working-with-certificates.md)
