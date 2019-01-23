---
title: Importazione di metadati personalizzati per un'estensione WCF
ms.date: 03/30/2017
ms.assetid: 78beb28f-408a-4c75-9c3c-caefe9595b1a
ms.openlocfilehash: b99d7fbab08c5edabe3a08baf89dd267c3f9fa25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562102"
---
# <a name="importing-custom-metadata-for-a-wcf-extension"></a>Importazione di metadati personalizzati per un'estensione WCF
In Windows Communication Foundation (WCF), l'importazione dei metadati è il processo di generazione di una rappresentazione astratta di un servizio o sue parti componenti dai relativi metadati. Ad esempio, è possibile importare WCF <xref:System.ServiceModel.Description.ServiceEndpoint> istanze <xref:System.ServiceModel.Channels.Binding> istanze o <xref:System.ServiceModel.Description.ContractDescription> istanze da un file WSDL di documento per un servizio. Per importare i metadati del servizio in WCF, usare un'implementazione del <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> classe astratta. Tipi che derivano dal <xref:System.ServiceModel.Description.MetadataImporter> classi implementano il supporto per l'importazione formati dei metadati che sfruttano il WS-Policy Importa per la logica in WCF.  
  
 I metadati personalizzati sono costituiti da elementi XML non importabili mediante le utilità di importazione dei metadati forniti dal sistema. Esempi comuni di metadati personalizzati sono le estensioni WSDL personalizzate e le asserzioni di criteri personalizzate.  
  
 Questa sezione descrive come importare le estensioni WSDL e le asserzioni di criteri personalizzate, senza tuttavia tratta il processo di importazione in sé. Per altre informazioni su come usare i tipi che esportano e importano metadati indipendentemente dal fatto i metadati sono personalizzate o di sistema supportate, vedere [esportazione e importazione di metadati](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
## <a name="overview"></a>Panoramica  
 Il <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> il tipo è l'implementazione del <xref:System.ServiceModel.Description.MetadataImporter> incluso con WCF classe astratta. Il tipo <xref:System.ServiceModel.Description.WsdlImporter> importa metadati WSDL insieme ai relativi criteri allegati. Questi elementi vengono quindi raggruppati in un oggetto <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType>. Le asserzioni di criteri e le estensioni WSDL non riconosciute dalle unità di importazione predefinite vengono importate tramite una delle unità di importazione personalizzate e registrate di documenti WSDL e di criteri. In genere, le unità di importazione vengono implementate per supportare gli elementi di associazione definiti dall'utente o per modificare il contratto importato.  
  
 Contenuto della sezione sono descritti gli argomenti seguenti:  
  
1.  Implementazione e utilizzo dell'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>, che espone i dati WSDL alle unità di importazione personalizzate prima di generare descrizioni e codice. Questa interfaccia può essere utilizzata per esaminare o modificare i tipi di descrizione e la compilazione del codice eseguita utilizzando un determinato set di metadati.  
  
2.  Implementazione e utilizzo dell'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType>, che espone le asserzioni di criteri alle unità di importazione prima di generare oggetti descrizione. Questa interfaccia può essere utilizzata per esaminare o modificare l'associazione o il contratto in base ai criteri scaricati.  
  
 Per altre informazioni sull'esportazione di asserzioni di criteri e WSDL personalizzata, vedere [esportazione di metadati personalizzati per un'estensione WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="importing-custom-wsdl-extensions"></a>Importazione di estensioni WSDL personalizzate  
 Per includere il supporto per l'importazione di estensioni WSDL, implementare l'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension> e quindi aggiungere tale implementazione alla proprietà <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A>. È inoltre possibile utilizzare il tipo <xref:System.ServiceModel.Description.WsdlImporter> per caricare implementazioni dell'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension> registrate nel file di configurazione dell'applicazione. Si noti che alcune unità di importazione WSDL sono registrate per impostazione predefinita e che l'ordine delle unità di importazione WSDL registrate è rilevante.  
  
 Quando l'unità di importazione WSDL personalizzata viene caricata e utilizzata dal tipo <xref:System.ServiceModel.Description.WsdlImporter>, prima di eseguire il processo di importazione il sistema chiama il metodo <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%2A> per consentire la modifica dei metadati. Quindi, dopo aver importato i contratti, il sistema chiama il metodo <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%2A> per consentire la modifica dei contratti importati dai metadati. Infine, il sistema chiama il metodo <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%2A> per consentire la modifica degli endpoint importati.  
  
 Per altre informazioni, vedere [Procedura: Importare informazioni WSDL personalizzate](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md).  
  
### <a name="importing-custom-policy-assertions"></a>Importazione di asserzioni di criteri personalizzati  
 Il <xref:System.ServiceModel.Description.WsdlImporter> tipo e il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) gestiscono automaticamente l'elaborazione di un'ampia gamma di tipi di asserzione di criteri nelle espressioni di criteri allegate ai documenti WSDL. Questi strumenti raccolgono, normalizzano e uniscono le espressioni di criteri allegate alle associazioni e alle porte WSDL.  
  
 Per includere il supporto per l'importazione di asserzioni di criteri personalizzate, implementare l'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension> e quindi aggiungere tale implementazione alla proprietà <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>. È inoltre possibile utilizzare il tipo <xref:System.ServiceModel.Description.MetadataImporter> per caricare implementazioni dell'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension> registrate nel file di configurazione dell'applicazione. Si noti che alcune unità di importazione dei criteri sono registrate per impostazione predefinita e che l'ordine delle unità di importazione dei criteri registrate è rilevante.  
  
 Il sistema dei metadati chiama più volte il metodo <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> in tutte le estensioni di importazione criteri registrate per ogni combinazione di alternative criteri allegate ai soggetti di criterio di messaggio, operazione ed endpoint. Quando si importa una porta WSDL, i criteri allegati alla porta e all'associazione WSDL corrispondente vengono uniti prima di chiamare le estensioni di importazione criteri. Le alternative criteri sono rese disponibili sottoforma di oggetti <xref:System.ServiceModel.Description.PolicyConversionContext> tramite un contesto <xref:System.ServiceModel.Description.PolicyAssertionCollection>. Ogni oggetto <xref:System.ServiceModel.Description.PolicyAssertionCollection> è una raccolta di asserzioni di criteri rappresentato dagli oggetti <xref:System.Xml.XmlElement>.  
  
 Le proprietà <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A> e <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A> dell'oggetto <xref:System.ServiceModel.Description.PolicyConversionContext> espongono gli oggetti <xref:System.ServiceModel.Description.ContractDescription> e <xref:System.ServiceModel.Channels.BindingElement> importati dal documento WSDL. Le estensioni di importazione criteri elaborano le asserzioni di criteri individuando le istanze di un determinato tipo di asserzione di criteri, apportando le modifiche corrispondenti agli oggetti <xref:System.ServiceModel.Description.ContractDescription> o <xref:System.ServiceModel.Channels.BindingElement> e quindi rimuovendo le asserzioni di criteri dall'istanza <xref:System.ServiceModel.Description.PolicyAssertionCollection> corrispondente.  
  
 Poiché l'attributo `wsp:Optional` e le espressioni di criteri annidate non sono normalizzate, le estensioni di importazione criteri devono gestire questi costrutti di criterio. Inoltre, poiché le estensioni di importazione criteri possono essere chiamate più volte con gli stessi oggetti <xref:System.ServiceModel.Description.ContractDescription> e <xref:System.ServiceModel.Channels.BindingElement>, le estensioni di importazione criteri devono essere in grado di gestire questo tipo di comportamento.  
  
> [!IMPORTANT]
>  È possibile che all'unità di importazione vengano passati metadati non validi o inappropriati. È pertanto necessario garantire che le unità di importazione personalizzate siano in grado di gestire qualsiasi formato XML.  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Importare informazioni WSDL personalizzate](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)
- [Procedura: Importa asserzioni di criteri personalizzate](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)
- [Procedura: Scrivere un'estensione per ServiceContractGenerator](../../../../docs/framework/wcf/extending/how-to-write-an-extension-for-the-servicecontractgenerator.md)
