---
title: Pubblicazione di metadati
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 031a80c52c194f300d7785f05e73eabeebb296b7
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="publishing-metadata"></a>Pubblicazione di metadati
I servizi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] pubblicano metadati tramite la pubblicazione di uno o più endpoint dei metadati. La pubblicazione di metadati del servizio rende disponibili i metadati utilizzando protocolli standard, ad esempio le richieste WS-MetadataExchange (MEX) e HTTP/GET. Gli endpoint dei metadati sono simili ad altri endpoint del servizio per indirizzo, associazione e contratto e possono essere aggiunti a un host del servizio tramite configurazione o codice imperativo.  
  
## <a name="publishing-metadata-endpoints"></a>Pubblicazione di endpoint dei metadati  
 Per pubblicare endpoint dei metadati per un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], è innanzitutto necessario aggiungere al servizio il comportamento del servizio <xref:System.ServiceModel.Description.ServiceMetadataBehavior>. L'aggiunta di un'istanza <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> consente al servizio di esporre gli endpoint dei metadati. Quando viene aggiunto il comportamento del servizio <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, è possibile esporre gli endpoint dei metadati che supportano il protocollo MEX o che rispondono alle richieste HTTP/GET.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> utilizza un oggetto <xref:System.ServiceModel.Description.WsdlExporter> per esportare i metadati per tutti gli endpoint nel servizio. Per ulteriori informazioni sull'esportazione di metadati da un servizio, vedere [esportazione e importazione di metadati](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> aggiunge un'istanza <xref:System.ServiceModel.Description.ServiceMetadataExtension> come estensione all'host del servizio. <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> fornisce l'implementazione per i metadati che pubblicano protocolli. È inoltre possibile utilizzare <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> per ottenere i metadati del servizio in fase di esecuzione accedendo alla proprietà <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>.  
  
### <a name="mex-metadata-endpoints"></a>Endpoint dei metadati MEX  
 Per aggiungere endpoint dei metadati che utilizzano il protocollo MEX, aggiungere gli endpoint del servizio all'host del servizio che utilizza il contratto di servizio `IMetadataExchange`. In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è inclusa un'interfaccia <xref:System.ServiceModel.Description.IMetadataExchange> con il nome di questo contratto di servizio che è possibile utilizzare come parte del modello di programmazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Gli endpoint WS-MetadataExchange o MEX, possono utilizzare una delle quattro associazioni predefinite che i metodi factory statici espongono sulla classe <xref:System.ServiceModel.Description.MetadataExchangeBindings> in modo che corrispondano alle associazioni predefinite utilizzate dagli strumenti [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], ad esempio Svcutil.exe. È inoltre possibile configurare gli endpoint dei metadati MEX utilizzando un'associazione personalizzata.  
  
### <a name="http-get-metadata-endpoints"></a>Endpoint dei metadati HTTP GET  
 Per aggiungere un endpoint dei metadati al servizio che risponda alle richieste HTTP/GET, impostare la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> in <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> su `true`. È inoltre possibile configurare un endpoint dei metadati che utilizza HTTPS impostando la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> in <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> su `true`.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Pubblicare metadati per un servizio usando un file di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Illustra come configurare un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per pubblicare metadati in modo che i client possano recuperare i metadati utilizzando una richiesta WS-MetadataExchange o HTTP/GET tramite la stringa di query `?wsdl`.  
  
 [Procedura: Pubblicare metadati per un servizio usando il codice](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Illustra come consentire la pubblicazione di metadati per un servizio nel codice [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in modo che i client possano recuperare i metadati utilizzando una richiesta WS-MetadataExchange o HTTP/GET tramite la stringa di query `?wsdl`.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>Vedere anche  
 [Esportazione e importazione di metadati](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
