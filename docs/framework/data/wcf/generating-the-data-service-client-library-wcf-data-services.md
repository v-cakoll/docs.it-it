---
title: Generazione della libreria dati del servizio dati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: f73ea93fe76f31c81935dbfb29183c247e41d8cd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975279"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="17300-102">Generazione della libreria dati del servizio dati (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="17300-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="17300-103">Un servizio dati che implementa il Open Data Protocol (OData) può restituire un documento di metadati del servizio che descrive il modello di dati esposto dal feed OData.</span><span class="sxs-lookup"><span data-stu-id="17300-103">A data service that implements the Open Data Protocol (OData) can return a service metadata document that describes the data model exposed by the OData feed.</span></span> <span data-ttu-id="17300-104">Per ulteriori informazioni, vedere [OData: documento dei metadati del servizio](https://go.microsoft.com/fwlink/?LinkId=186070).</span><span class="sxs-lookup"><span data-stu-id="17300-104">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="17300-105">È possibile usare la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio per aggiungere un riferimento a un servizio basato su OData.</span><span class="sxs-lookup"><span data-stu-id="17300-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an OData-based service.</span></span> <span data-ttu-id="17300-106">Quando si utilizza questo strumento per aggiungere un riferimento ai metadati restituiti da un feed OData in un progetto client, vengono eseguite le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="17300-106">When you use this tool to add a reference to the metadata returned by an OData feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="17300-107">Richiesta del documento dei metadati del servizio al servizio dati e interpretazione dei metadati restituiti.</span><span class="sxs-lookup"><span data-stu-id="17300-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="17300-108">I metadati restituiti vengono archiviati nel progetto client come file con estensione edmx.</span><span class="sxs-lookup"><span data-stu-id="17300-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="17300-109">Non è possibile aprire questo file con estensione edmx usando Entity Data Model Designer perché non presenta lo stesso formato di un file con estensione edmx usato da Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="17300-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="17300-110">È possibile visualizzare questo file di metadati usando l'editor XML o qualsiasi editor di testo.</span><span class="sxs-lookup"><span data-stu-id="17300-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="17300-111">Per ulteriori informazioni, vedere la [\[MC-EDMX\]: Entity Data Model per la specifica del formato di pacchetti di servizi dati](https://go.microsoft.com/fwlink/?LinkID=178833)</span><span class="sxs-lookup"><span data-stu-id="17300-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
- <span data-ttu-id="17300-112">Generazione di una rappresentazione del servizio come classe contenitore di entità che eredita da <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="17300-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="17300-113">Il comportamento di questa classe contenitore di entità generata è simile a quello del contenitore di entità generato dagli strumenti di Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="17300-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="17300-114">Per altre informazioni, vedere [Cenni preliminari su Object Services (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="17300-114">For more information, see [Object Services Overview (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="17300-115">Generazione di classi di dati per i tipi di modello di dati individuati nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="17300-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="17300-116">Aggiunta di un riferimento all'assembly `System.Data.Services.Client` per il progetto.</span><span class="sxs-lookup"><span data-stu-id="17300-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="17300-117">Per altre informazioni, vedere [procedura: aggiungere un riferimento al servizio dati](how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="17300-117">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="17300-118">Le classi del servizio dati client possono inoltre essere generate tramite lo strumento [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="17300-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="17300-119">Per altre informazioni, vedere [procedura: generare manualmente classi del servizio dati client](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="17300-119">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="17300-120">Mapping dei tipi di dati client</span><span class="sxs-lookup"><span data-stu-id="17300-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="17300-121">Quando si usa la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio o lo strumento `DataSvcUtil.exe` per generare classi di dati client basate su un feed OData, i tipi di dati del .NET Framework vengono mappati ai tipi primitivi del modello di dati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="17300-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an OData feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="17300-122">Tipo del modello di dati</span><span class="sxs-lookup"><span data-stu-id="17300-122">Data model type</span></span>|<span data-ttu-id="17300-123">Tipi di dati di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="17300-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="17300-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="17300-124"><xref:System.Byte> `[]`</span></span>|  
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
  
 <span data-ttu-id="17300-125">Per ulteriori informazioni, vedere [OData: tipi di dati primitivi](https://go.microsoft.com/fwlink/?LinkId=186072).</span><span class="sxs-lookup"><span data-stu-id="17300-125">For more information, see [OData: Primitive Data Types](https://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17300-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17300-126">See also</span></span>

- [<span data-ttu-id="17300-127">Libreria client WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="17300-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="17300-128">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="17300-128">Quickstart</span></span>](quickstart-wcf-data-services.md)
