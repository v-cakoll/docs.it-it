---
title: Esportazione di metadati personalizzati per un'estensione WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53c93882-f8ba-4192-965b-787b5e3f09c0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7615da8e718d75ba7d90e181ab756b3128bc82d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="exporting-custom-metadata-for-a-wcf-extension"></a>Esportazione di metadati personalizzati per un'estensione WCF
In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], l'esportazione dei metadati è il processo utilizzato per descrivere gli endpoint di un servizio e quindi proiettarli in una rappresentazione parallela standardizzata che i client possono utilizzare allo scopo di comprendere come utilizzare il servizio. I metadati personalizzati sono costituiti da elementi XML non esportabili mediante le unità di esportazione dei metadati forniti dal sistema. Questi metadati comprendono in genere elementi WSDL personalizzati di elementi di comportamenti e associazioni definiti dall'utente nonché asserzioni di criteri personalizzate relative alle funzionalità e ai requisiti di associazioni e contratti.  
  
 Questa sezione descrive come esportare elementi WSDL o asserzioni di criteri personalizzati, senza tuttavia trattare il processo di esportazione in sé. Per ulteriori informazioni su come usare i tipi di esportare e importano metadati indipendentemente dai metadati personalizzati o costruito sistema, vedere [di esportazione e importazione di metadati](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
## <a name="overview"></a>Panoramica  
 Quando si pubblicano i metadati tramite il comportamento <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, il sistema analizza la descrizione <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> e quindi genera elementi XSD e WSDL (comprese le asserzioni di criteri) per tutti i contratti e le associazioni che [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è in grado di supportare utilizzando attributi e associazioni forniti dal sistema. Tuttavia, l'esportazione degli elementi relativi agli attributi e alle associazioni aventi un comportamento personalizzato richiede un supporto specifico.  
  
 Contenuto della sezione sono descritti gli argomenti seguenti:  
  
1.  Come implementare e utilizzare l'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> che espone all'utente i dati da generare in WSDL prima di pubblicarli.  
  
2.  Come implementare e utilizzare l'interfaccia <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> che espone all'utente i dati dei criteri prima di esportare le asserzioni di criteri nei dati WSDL.  
  
 Per ulteriori informazioni sull'importazione WSDL personalizzate e le asserzioni di criteri, vedere [l'importazione di metadati personalizzati per un'estensione WCF](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-custom-wsdl-elements"></a>Esportazione di elementi WSDL personalizzati  
 Implementare l'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension> in un comportamento di operazione, contratto, endpoint o elemento di associazione (rispettivamente <xref:System.ServiceModel.Description.IOperationBehavior>, <xref:System.ServiceModel.Description.IContractBehavior>, <xref:System.ServiceModel.Description.IEndpointBehavior> o <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>) e aggiungere i comportamenti o gli elementi di associazione nella descrizione del servizio da esportare. (Per ulteriori informazioni sull'inserimento di comportamenti, vedere [la configurazione e l'estensione del Runtime con i comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)). L'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension> viene chiamata per ogni endpoint, che quindi esporta il contratto a meno che non sia stato già esportato. A seconda delle proprie esigenze, è possibile ricorrere a uno dei due processi di esportazione:  
  
-   Utilizzare il contesto <xref:System.ServiceModel.Description.WsdlContractConversionContext> per modificare i metadati esportati tramite il metodo <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A>.  
  
-   Utilizzare il contesto <xref:System.ServiceModel.Description.WsdlEndpointConversionContext> per modificare i metadati dell'endpoint esportati tramite il metodo <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A>.  
  
 Il metodo <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A> viene chiamato in tutte le implementazioni dell'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension> all'interno dell'istanza della descrizione <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType> da esportare.  Il metodo <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> viene chiamato in tutte le implementazioni dell'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension> all'interno dell'istanza della descrizione <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> da esportare.  
  
 Per ulteriori informazioni, vedere [procedura: esportazione WSDL personalizzata](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md) e l'esempio [pubblicazione WSDL personalizzata](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md).  
  
## <a name="exporting-custom-policy-assertions"></a>Esportazione di asserzioni di criteri personalizzati  
 Per scrivere asserzioni di criteri personalizzate relative al supporto delle associazioni e alle funzionalità di contratto nel codice WSDL, implementare l'interfaccia <xref:System.ServiceModel.Description.IPolicyExportExtension> in un elemento <xref:System.ServiceModel.Channels.BindingElement> e aggiungere l'elemento di associazione all'associazione. L'interfaccia, <xref:System.ServiceModel.Description.IPolicyExportExtension> dopo essere stata chiamata una volta durante l'esportazione dell'elemento di associazione implementato contenuto in un'associazione, passa il contesto <xref:System.ServiceModel.Description.PolicyConversionContext> al metodo <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>. È possibile utilizzare i metodi dell'istanza del contesto <xref:System.ServiceModel.Description.PolicyConversionContext> per aggiungere elementi alle asserzioni di criteri allegate ai soggetti di messaggio, operazione o endpoint dell'associazione WSDL.  
  
 Per ulteriori informazioni, vedere [procedura: esportare asserzioni di criteri personalizzata](../../../../docs/framework/wcf/extending/how-to-export-custom-policy-assertions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: esportare informazioni WSDL personalizzate](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md)  
 [Procedura: esportare asserzioni di criteri personalizzati](../../../../docs/framework/wcf/extending/how-to-export-custom-policy-assertions.md)  
 [Importazione di metadati personalizzati per un'estensione WCF](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)
