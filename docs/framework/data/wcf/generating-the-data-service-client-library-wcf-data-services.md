---
title: Generazione della libreria dati del servizio dati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: b550af85bcd4bec30707721c6549c7b9094bfd1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630905"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generazione della libreria dati del servizio dati (WCF Data Services)
Un servizio dati che implementa il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] può restituire un documento di metadati di servizio che descrive il modello di dati esposto dal [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed. Per altre informazioni, vedere [OData: Documento di metadati di servizio](https://go.microsoft.com/fwlink/?LinkId=186070). È possibile usare la **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio per aggiungere un riferimento a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-servizio basato su. Quando si usa questo strumento per aggiungere un riferimento ai metadati restituiti da un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in un progetto client, esegue le azioni seguenti:  
  
-   Richiesta del documento dei metadati del servizio al servizio dati e interpretazione dei metadati restituiti.  
  
    > [!NOTE]
    >  I metadati restituiti vengono archiviati nel progetto client come file con estensione edmx. Non è possibile aprire questo file con estensione edmx usando Entity Data Model Designer perché non presenta lo stesso formato di un file con estensione edmx usato da Entity Framework. È possibile visualizzare questo file di metadati usando l'editor XML o qualsiasi editor di testo. Per altre informazioni, vedere la [ \[MC-EDMX\]: Entity Data Model per il formato dei pacchetti di servizi dati](https://go.microsoft.com/fwlink/?LinkID=178833) specifica  
  
-   Generazione di una rappresentazione del servizio come classe contenitore di entità che eredita da <xref:System.Data.Services.Client.DataServiceContext>. Il comportamento di questa classe contenitore di entità generata è simile a quello del contenitore di entità generato dagli strumenti di Entity Data Model. Per altre informazioni, vedere [Cenni preliminari su Object Services (Entity Framework)](https://msdn.microsoft.com/library/43014cf9-c9cb-4538-bfbb-197820b60038).  
  
-   Generazione di classi di dati per i tipi di modello di dati individuati nei metadati del servizio.  
  
-   Aggiunta di un riferimento all'assembly `System.Data.Services.Client` per il progetto.  
  
 Per altre informazioni, vedere [Procedura: Aggiungere un riferimento al servizio dati](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Le classi del servizio dati client possono essere generate anche usando il [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) strumento al prompt dei comandi. Per altre informazioni, vedere [Procedura: Generare manualmente classi del servizio dati Client](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Mapping dei tipi di dati client  
 Quando si usa la **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio o il `DataSvcUtil.exe` dello strumento per generare classi dati client basate su un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, i tipi di dati .NET Framework vengono mappati ai tipi primitivi dal modello di dati come indicato di seguito:  
  
|Tipo del modello di dati|Tipi di dati di .NET Framework|  
|---------------------|------------------------------|  
|`Edm.Binary`|<xref:System.Byte> `[]`|  
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
  
 Per altre informazioni, vedere [OData: Tipi di dati primitivi](https://go.microsoft.com/fwlink/?LinkId=186072).  
  
## <a name="see-also"></a>Vedere anche
- [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Guida rapida](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
