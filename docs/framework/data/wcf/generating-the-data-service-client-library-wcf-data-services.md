---
title: Generazione della libreria dati del servizio dati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 14ea550715c1b224945137f123eed3b53e56cead
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918648"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generazione della libreria dati del servizio dati (WCF Data Services)
Un servizio dati che implementa l' [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] oggetto può restituire un documento [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] di metadati del servizio che descrive il modello di dati esposto dal feed. Per ulteriori informazioni, vedere [OData: Documento](https://go.microsoft.com/fwlink/?LinkId=186070)di metadati del servizio. È possibile usare la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio per aggiungere un riferimento [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]a un servizio basato su. Quando si utilizza questo strumento per aggiungere un riferimento ai metadati restituiti da un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in un progetto client, vengono eseguite le azioni seguenti:  
  
- Richiesta del documento dei metadati del servizio al servizio dati e interpretazione dei metadati restituiti.  
  
    > [!NOTE]
    > I metadati restituiti vengono archiviati nel progetto client come file con estensione edmx. Non è possibile aprire questo file con estensione edmx usando Entity Data Model Designer perché non presenta lo stesso formato di un file con estensione edmx usato da Entity Framework. È possibile visualizzare questo file di metadati usando l'editor XML o qualsiasi editor di testo. Per ulteriori informazioni, vedere [ \[MC-edmx\]: Entity Data Model per la specifica del formato](https://go.microsoft.com/fwlink/?LinkID=178833) di pacchetti di servizi dati  
  
- Generazione di una rappresentazione del servizio come classe contenitore di entità che eredita da <xref:System.Data.Services.Client.DataServiceContext>. Il comportamento di questa classe contenitore di entità generata è simile a quello del contenitore di entità generato dagli strumenti di Entity Data Model. Per altre informazioni, vedere [Cenni preliminari su Object Services (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).  
  
- Generazione di classi di dati per i tipi di modello di dati individuati nei metadati del servizio.  
  
- Aggiunta di un riferimento all'assembly `System.Data.Services.Client` per il progetto.  
  
 Per altre informazioni, vedere [Procedura: Aggiungere un riferimento](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)al servizio dati.  
  
 Le classi del servizio dati client possono inoltre essere generate tramite lo strumento [DataSvcUtil. exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) al prompt dei comandi. Per altre informazioni, vedere [Procedura: Generare manualmente classi](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)del servizio dati client.  
  
## <a name="client-data-type-mapping"></a>Mapping dei tipi di dati client  
 Quando si utilizza la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio `DataSvcUtil.exe` o lo strumento per generare classi di dati client basate su [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] un feed, i tipi di dati .NET Framework vengono mappati ai tipi primitivi del modello di dati nel modo seguente:  
  
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
  
 Per ulteriori informazioni, vedere [OData: Tipi](https://go.microsoft.com/fwlink/?LinkId=186072)di dati primitivi.  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Guida rapida](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
