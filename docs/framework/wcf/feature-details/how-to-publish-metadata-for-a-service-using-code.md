---
title: 'Procedura: pubblicare metadati per un servizio usando codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
ms.openlocfilehash: db6bca8728789879f9bfea40904bfc80352d1dbe
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144916"
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a><span data-ttu-id="c2740-102">Procedura: pubblicare metadati per un servizio usando codice</span><span class="sxs-lookup"><span data-stu-id="c2740-102">How to: Publish Metadata for a Service Using Code</span></span>
<span data-ttu-id="c2740-103">Questo è uno dei due argomenti sulle procedure che illustrano la pubblicazione di metadati per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c2740-103">This is one of two how-to topics that discuss publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="c2740-104">Esistono due modi per specificare come un servizio dovrebbe pubblicare metadati: usando un file di configurazione o il codice.</span><span class="sxs-lookup"><span data-stu-id="c2740-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="c2740-105">In questo argomento viene illustrato come pubblicare metadati per un servizio utilizzando un codice.</span><span class="sxs-lookup"><span data-stu-id="c2740-105">This topic shows how to publish metadata for a service using a code.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="c2740-106">In questo argomento viene illustrato come pubblicare metadati in modo non sicuro.</span><span class="sxs-lookup"><span data-stu-id="c2740-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="c2740-107">Qualsiasi client può recuperare i metadati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="c2740-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="c2740-108">Se è necessario che il servizio pubblichi metadati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="c2740-108">If you require your service to publish metadata in a secure manner.</span></span> <span data-ttu-id="c2740-109">vedere [endpoint di metadati protetti personalizzato](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="c2740-109">see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="c2740-110">Per altre informazioni sulla pubblicazione di metadati in un file di configurazione, vedere [procedura: pubblicare metadati per un servizio usando un file di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c2740-110">For more information about publishing metadata in a configuration file, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span> <span data-ttu-id="c2740-111">La pubblicazione di metadati consente ai client di recuperare i metadati usando una richiesta GET WS-Transfer o una richiesta HTTP/GET tramite la stringa di query `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="c2740-111">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="c2740-112">Per essere certi che il codice funzioni, è necessario creare un servizio WCF di base.</span><span class="sxs-lookup"><span data-stu-id="c2740-112">To be sure that the code is working you must create a basic WCF service.</span></span> <span data-ttu-id="c2740-113">Nel codice seguente viene fornito un servizio indipendente di base.</span><span class="sxs-lookup"><span data-stu-id="c2740-113">A basic self-hosted service is provided in the following code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a><span data-ttu-id="c2740-114">Per pubblicare metadati nel codice</span><span class="sxs-lookup"><span data-stu-id="c2740-114">To publish metadata in code</span></span>  
  
1. <span data-ttu-id="c2740-115">All'interno del metodo principale di un'applicazione console, creare un'istanza di un oggetto <xref:System.ServiceModel.ServiceHost> passando il tipo di servizio e l'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="c2740-115">Within the main method of a console application, instantiate a <xref:System.ServiceModel.ServiceHost> object by passing in the service type and the base address.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2. <span data-ttu-id="c2740-116">Creare un blocco try subito sotto il codice per il passaggio 1. In tal modo verranno rilevate tutte le eccezioni generate mentre il servizio è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c2740-116">Create a try block immediately below the code for step 1, this catches any exceptions that get thrown while the service is running.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3. <span data-ttu-id="c2740-117">Controllare se l'host del servizio contiene già un <xref:System.ServiceModel.Description.ServiceMetadataBehavior>. In caso contrario, creare una nuova istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="c2740-117">Check to see whether the service host already contains a <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, if not, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4. <span data-ttu-id="c2740-118">Impostare la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> su `true.`</span><span class="sxs-lookup"><span data-stu-id="c2740-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true.`</span></span>  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5. <span data-ttu-id="c2740-119"><xref:System.ServiceModel.Description.ServiceMetadataBehavior> contiene una proprietà <xref:System.ServiceModel.Description.MetadataExporter>.</span><span class="sxs-lookup"><span data-stu-id="c2740-119">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contains a <xref:System.ServiceModel.Description.MetadataExporter> property.</span></span> <span data-ttu-id="c2740-120"><xref:System.ServiceModel.Description.MetadataExporter> contiene una proprietà <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2740-120">The <xref:System.ServiceModel.Description.MetadataExporter> contains a <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property.</span></span> <span data-ttu-id="c2740-121">Impostare il valore della proprietà <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> su <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2740-121">Set the value of the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>.</span></span> <span data-ttu-id="c2740-122">La proprietà <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> può essere impostata anche su <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2740-122">The <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property can also be set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>.</span></span> <span data-ttu-id="c2740-123">Se impostato su <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> , l'utilità di esportazione dei metadati genera informazioni sui criteri con i metadati conformi a ws-policy 1,5.</span><span class="sxs-lookup"><span data-stu-id="c2740-123">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> the metadata exporter generates policy information with the metadata that" conforms to WS-Policy 1.5.</span></span> <span data-ttu-id="c2740-124">mentre se è impostata su <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>, l'utilità di esportazione genera informazioni sui criteri con i metadati conformi a WS-Policy 1.2.</span><span class="sxs-lookup"><span data-stu-id="c2740-124">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> the metadata exporter generates policy information that conforms to WS-Policy 1.2.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6. <span data-ttu-id="c2740-125">Aggiungere l'istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior> alla raccolta di comportamenti dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="c2740-125">Add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance to the service host's behaviors collection.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7. <span data-ttu-id="c2740-126">Aggiungere l'endpoint di scambio dei metadati all'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="c2740-126">Add the metadata exchange endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8. <span data-ttu-id="c2740-127">Aggiungere un endpoint dell'applicazione all'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="c2740-127">Add an application endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    > <span data-ttu-id="c2740-128">Se non vengono aggiunti endpoint al servizio, il runtime aggiunge gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c2740-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="c2740-129">In questo esempio poiché l'oggetto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> del servizio è impostato su `true`, nel servizio è abilitata la pubblicazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="c2740-129">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, the service has publishing metadata enabled.</span></span> <span data-ttu-id="c2740-130">Per ulteriori informazioni sugli endpoint predefiniti, vedere [Configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c2740-130">For more information about default endpoints, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="c2740-131">Aprire l'host del servizio e attendere le chiamate in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c2740-131">Open the service host and wait for incoming calls.</span></span> <span data-ttu-id="c2740-132">Quando l'utente preme il tasto INVIO, chiudere l'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="c2740-132">When the user presses ENTER, close the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. <span data-ttu-id="c2740-133">Compilare ed eseguire l'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="c2740-133">Build and run the console application.</span></span>  
  
11. <span data-ttu-id="c2740-134">Utilizzare Internet Explorer per passare all'indirizzo di base del servizio ( `http://localhost:8001/MetadataSample` in questo esempio) e verificare che la pubblicazione dei metadati sia attivata.</span><span class="sxs-lookup"><span data-stu-id="c2740-134">Use Internet Explorer to browse to the base address of the service (`http://localhost:8001/MetadataSample` in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="c2740-135">Dovrebbe venire visualizzata una pagina Web con scritto "Simple Service" in alto, seguito subito sotto da "È stato creato un servizio".</span><span class="sxs-lookup"><span data-stu-id="c2740-135">You should see a Web page displayed that says "Simple Service" at the top and immediately below "You have created a service."</span></span> <span data-ttu-id="c2740-136">Se così non fosse, all'inizio della pagina risultante verrà visualizzato il messaggio: "La pubblicazione dei metadati per il servizio è attualmente disabilitata".</span><span class="sxs-lookup"><span data-stu-id="c2740-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2740-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2740-137">Example</span></span>  
 <span data-ttu-id="c2740-138">Nell'esempio di codice seguente viene illustrata l'implementazione di un servizio WCF di base che pubblica i metadati per il servizio nel codice.</span><span class="sxs-lookup"><span data-stu-id="c2740-138">The following code example shows the implementation of a basic WCF service that publishes metadata for the service in code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="c2740-139">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c2740-139">See also</span></span>

- [<span data-ttu-id="c2740-140">Procedura: ospitare un servizio WCF in un'applicazione gestita</span><span class="sxs-lookup"><span data-stu-id="c2740-140">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="c2740-141">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="c2740-141">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="c2740-142">Panoramica dell'architettura dei metadati</span><span class="sxs-lookup"><span data-stu-id="c2740-142">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
- [<span data-ttu-id="c2740-143">Uso di metadati</span><span class="sxs-lookup"><span data-stu-id="c2740-143">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [<span data-ttu-id="c2740-144">Procedura: pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="c2740-144">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
