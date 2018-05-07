---
title: 'Procedura: importare asserzioni di criteri personalizzati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f41d787-accb-4a10-bfc6-a807671d1581
ms.openlocfilehash: b6155296e264bb3ae90aac2ee6b83797e632962e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-import-custom-policy-assertions"></a>Procedura: importare asserzioni di criteri personalizzati
Le asserzioni di criteri descrivono le funzionalità e i requisiti di un endpoint del servizio.  Le applicazioni client possono utilizzare asserzioni di criteri nei metadati del servizio per configurare l'associazione del client o per personalizzare il contratto di servizio per un endpoint del servizio.  
  
 Le asserzioni di criteri personalizzate vengono importate implementando l'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> e passando quell'oggetto al sistema di metadati o registrando il tipo di implementazione nel file di configurazione dell'applicazione.  Le implementazioni dell'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension> devono fornire un costruttore predefinito.  
  
### <a name="to-import-custom-policy-assertions"></a>Per importare asserzioni di criteri personalizzati  
  
1.  Implementare l'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> in una classe. Vedere le procedure seguenti.  
  
2.  Inserire l'unità di importazione dei criteri personalizzati tramite uno dei modi seguenti:  
  
3.  Utilizzando un file di configurazione. Vedere le procedure seguenti.  
  
4.  Utilizzo di un file di configurazione con [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Vedere le procedure seguenti.  
  
5.  Inserendo a livello di programmazione l'unità di importazione dei criteri. Vedere le procedure seguenti.  
  
### <a name="to-implement-the-systemservicemodeldescriptionipolicyimportextension-interface-on-any-class"></a>Per implementare l'interfaccia System.ServiceModel.Description.IPolicyImportExtension in qualsiasi classe  
  
1.  Nel metodo <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, per ogni oggetto criterio a cui si è interessati, individuare le asserzioni dei criteri che si desidera importare chiamando il metodo appropriato (in base all'ambito dell'asserzione desiderata) nell'oggetto <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> passato al metodo. Nell'esempio di codice seguente viene illustrato come utilizzare il metodo <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> per individuare l'asserzione del criterio personalizzato e rimuoverla dalla raccolta in un passaggio. Se si utilizza il metodo di rimozione per individuare e rimuovere l'asserzione, non è necessario eseguire il passaggio 4.  
  
     [!code-csharp[CustomPolicySample#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyimporter.cs#9)]
     [!code-vb[CustomPolicySample#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyimporter.vb#9)]  
  
2.  Elaborare le asserzioni dei criteri. Si noti che il sistema del criterio non normalizza i criteri annidati e `wsp:optional`. È necessario elaborare questi costrutti nell'implementazione di un'estensione di importazione del criterio.  
  
3.  Eseguire la personalizzazione dell'associazione o del contratto che supporta la funzionalità o il requisito specificato dall'asserzione del criterio. In genere, le asserzioni indicano che un'associazione richiede una particolare configurazione o uno specifico elemento di associazione. Apportare queste modifiche accedendo alla proprietà <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=nameWithType>. Le altre asserzioni richiedono che si modifichi il contratto.  È possibile accedere e modificare il contratto utilizzando la proprietà <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=nameWithType>.  Si noti che l'unità di importazione dei criteri può venire chiamata più volte per la stessa associazione e per lo stesso contratto, ma per alternative criteri diverse se l'importazione di un'alternativa criterio non riesce. Il codice deve adattarsi a questo comportamento.  
  
4.  Rimuovere l'asserzione di criteri personalizzata dalla raccolta di asserzioni. Se non si rimuove l'asserzione di Windows Communication Foundation (WCF) presuppone che l'importazione dei criteri non è riuscita e non importa l'associazione associata. Se è stato utilizzato il metodo <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> per individuare l'asserzione di criteri personalizzata e rimuoverla dalla raccolta in un unico passaggio, non è necessario eseguire questa procedura.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-a-configuration-file"></a>Per inserire l'unità di importazione di criteri personalizzata nel sistema di metadati utilizzando un file di configurazione  
  
1.  Aggiungere il tipo di unità di importazione per il `<extensions>` elemento all'interno di [ \<policyImporters >](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) elemento nel file di configurazione del client.  
  
     [!code-xml[CustomPolicySample#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.exe.config#7)]   
  
2.  Nell'applicazione client, utilizzare <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> per risolvere i metadati. L'unità di importazione viene richiamata automaticamente.  
  
     [!code-csharp[CustomPolicySample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.cs#10)]
     [!code-vb[CustomPolicySample#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.vb#10)]  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-svcutilexe"></a>Per inserire l'unità di importazione di criteri personalizzata nel sistema di metadati utilizzando Svcutil.exe  
  
1.  Aggiungere il tipo di unità di importazione per il `<extensions>` elemento all'interno di [ \<policyImporters >](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) elemento nel file di configurazione di svcutil.exe. config. È anche possibile puntare a Svcutil.exe per caricare tipi di unità di importazione di criteri registrati in un file di configurazione diverso, utilizzando l'opzione `/svcutilConfig`.  
  
2.  Utilizzare [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per importare i metadati e l'utilità di importazione viene richiamata automaticamente.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-programmatically"></a>Per inserire l'unità di importazione di criteri personalizzata nel sistema di metadati a livello di programmazione  
  
1.  Aggiungere l'unità di importazione alla proprietà <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=nameWithType> (ad esempio, se si sta utilizzando <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>) prima di importare i metadati.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>  
 [Estensione del sistema di metadati](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)
