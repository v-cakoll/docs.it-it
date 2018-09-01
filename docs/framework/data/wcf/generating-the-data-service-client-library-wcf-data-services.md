---
title: Generazione della libreria dati del servizio dati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 170f9714f3cfbf2350423f28316d665d427fd56e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389374"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="c2a0e-102">Generazione della libreria dati del servizio dati (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="c2a0e-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="c2a0e-103">Un servizio dati che implementa il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] può restituire un documento di metadati di servizio che descrive il modello di dati esposto dal [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="c2a0e-104">Per altre informazioni, vedere [OData: documento dei metadati del servizio](https://go.microsoft.com/fwlink/?LinkId=186070).</span><span class="sxs-lookup"><span data-stu-id="c2a0e-104">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="c2a0e-105">È possibile usare la **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio per aggiungere un riferimento a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-servizio basato su.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="c2a0e-106">Quando si usa questo strumento per aggiungere un riferimento ai metadati restituiti da un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in un progetto client, esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2a0e-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
-   <span data-ttu-id="c2a0e-107">Richiesta del documento dei metadati del servizio al servizio dati e interpretazione dei metadati restituiti.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c2a0e-108">I metadati restituiti vengono archiviati nel progetto client come file con estensione edmx.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="c2a0e-109">Non è possibile aprire questo file con estensione edmx usando Entity Data Model Designer perché non presenta lo stesso formato di un file con estensione edmx usato da Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="c2a0e-110">È possibile visualizzare questo file di metadati usando l'editor XML o qualsiasi editor di testo.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="c2a0e-111">Per altre informazioni, vedere la [ \[MC-EDMX\]: Entity Data Model per il formato dei pacchetti di servizi dati](https://go.microsoft.com/fwlink/?LinkID=178833) specifica</span><span class="sxs-lookup"><span data-stu-id="c2a0e-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
-   <span data-ttu-id="c2a0e-112">Generazione di una rappresentazione del servizio come classe contenitore di entità che eredita da <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="c2a0e-113">Il comportamento di questa classe contenitore di entità generata è simile a quello del contenitore di entità generato dagli strumenti di Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="c2a0e-114">Per altre informazioni, vedere [Cenni preliminari su Object Services (Entity Framework)](https://msdn.microsoft.com/library/43014cf9-c9cb-4538-bfbb-197820b60038).</span><span class="sxs-lookup"><span data-stu-id="c2a0e-114">For more information, see [Object Services Overview (Entity Framework)](https://msdn.microsoft.com/library/43014cf9-c9cb-4538-bfbb-197820b60038).</span></span>  
  
-   <span data-ttu-id="c2a0e-115">Generazione di classi di dati per i tipi di modello di dati individuati nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
-   <span data-ttu-id="c2a0e-116">Aggiunta di un riferimento all'assembly `System.Data.Services.Client` per il progetto.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="c2a0e-117">Per altre informazioni, vedere [procedura: aggiungere un riferimento al servizio dati](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c2a0e-117">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="c2a0e-118">Le classi del servizio dati client possono essere generate anche usando il [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) strumento al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="c2a0e-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="c2a0e-119">Per altre informazioni, vedere [procedura: manualmente generare classi dati Client del servizio](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c2a0e-119">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="c2a0e-120">Mapping dei tipi di dati client</span><span class="sxs-lookup"><span data-stu-id="c2a0e-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="c2a0e-121">Quando si usa la **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio o il `DataSvcUtil.exe` dello strumento per generare classi dati client basate su un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, i tipi di dati .NET Framework vengono mappati ai tipi primitivi dal modello di dati come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c2a0e-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="c2a0e-122">Tipo del modello di dati</span><span class="sxs-lookup"><span data-stu-id="c2a0e-122">Data model type</span></span>|<span data-ttu-id="c2a0e-123">Tipi di dati di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c2a0e-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="c2a0e-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="c2a0e-124"><xref:System.Byte> `[]`</span></span>|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 <span data-ttu-id="c2a0e-125">Per altre informazioni, vedere [OData: tipi di dati primitivi](https://go.microsoft.com/fwlink/?LinkId=186072).</span><span class="sxs-lookup"><span data-stu-id="c2a0e-125">For more information, see [OData: Primitive Data Types](https://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a0e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2a0e-126">See Also</span></span>  
 [<span data-ttu-id="c2a0e-127">Libreria client WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="c2a0e-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="c2a0e-128">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="c2a0e-128">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
