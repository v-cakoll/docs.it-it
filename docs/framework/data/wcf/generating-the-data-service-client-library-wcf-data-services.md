---
title: Generazione della libreria dati del servizio dati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: b938e419a5a650fe0e24445c44a67aead13349fa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348113"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generazione della libreria dati del servizio dati (WCF Data Services)
Un servizio dati che implementa il Open Data Protocol (OData) può restituire un documento di metadati del servizio che descrive il modello di dati esposto dal feed OData. Per ulteriori informazioni, vedere la sezione documento metadati del servizio nell'articolo relativo alla [Panoramica di OData](https://www.odata.org/documentation/odata-version-2-0/overview/) . È possibile usare la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio per aggiungere un riferimento a un servizio basato su OData. Quando si utilizza questo strumento per aggiungere un riferimento ai metadati restituiti da un feed OData in un progetto client, vengono eseguite le azioni seguenti:  
  
- Richiesta del documento dei metadati del servizio al servizio dati e interpretazione dei metadati restituiti.  
  
    > [!NOTE]
    > I metadati restituiti vengono archiviati nel progetto client come file con estensione edmx. Non è possibile aprire questo file con estensione edmx usando Entity Data Model Designer perché non presenta lo stesso formato di un file con estensione edmx usato da Entity Framework. È possibile visualizzare questo file di metadati usando l'editor XML o qualsiasi editor di testo. Per ulteriori informazioni, vedere [\[MC-EDMX\]: Entity Data Model per il formato di creazione dei pacchetti di servizi dati](https://docs.microsoft.com/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).
  
- Generazione di una rappresentazione del servizio come classe contenitore di entità che eredita da <xref:System.Data.Services.Client.DataServiceContext>. Il comportamento di questa classe contenitore di entità generata è simile a quello del contenitore di entità generato dagli strumenti di Entity Data Model. Per altre informazioni, vedere [Cenni preliminari su Object Services (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).  
  
- Generazione di classi di dati per i tipi di modello di dati individuati nei metadati del servizio.  
  
- Aggiunta di un riferimento all'assembly `System.Data.Services.Client` per il progetto.  
  
 Per altre informazioni, vedere [procedura: aggiungere un riferimento al servizio dati](how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Le classi del servizio dati client possono inoltre essere generate tramite lo strumento [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) al prompt dei comandi. Per altre informazioni, vedere [procedura: generare manualmente classi del servizio dati client](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Mapping dei tipi di dati client  
 Quando si usa la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio o lo strumento `DataSvcUtil.exe` per generare classi di dati client basate su un feed OData, i tipi di dati del .NET Framework vengono mappati ai tipi primitivi del modello di dati nel modo seguente:  
  
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
  
 Per ulteriori informazioni, vedere la sezione tipi di dati primitivi nell'articolo relativo alla [Panoramica di OData](https://www.odata.org/documentation/odata-version-2-0/overview/) .
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
- [Guida rapida](quickstart-wcf-data-services.md)
