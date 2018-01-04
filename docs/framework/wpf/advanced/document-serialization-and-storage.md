---
title: Serializzazione e archiviazione di documenti
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a232e1e2557bf1ecc6bb5f27f941e03a204aec6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="document-serialization-and-storage"></a>Serializzazione e archiviazione di documenti
[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] offre un ambiente avanzato per la creazione e la visualizzazione di documenti di alta qualità.  Funzionalità sofisticate che supportano documenti sia statici che dinamici e controlli di visualizzazione avanzati combinati con potenti funzionalità grafiche 2D e 3D consentono la creazione di applicazioni [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] di livello superiore in termini di qualità ed esperienza utente.  La possibilità di gestire in modo flessibile la rappresentazione in memoria di un documento è una funzionalità chiave di [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] e la capacità di salvare e caricare documenti in modo efficiente da un archivio dati è l'esigenza di quasi tutte le applicazioni.  Il processo di conversione di un documento da una rappresentazione in memoria interna a un archivio dati esterno è detto serializzazione.  Il processo inverso di lettura di un archivio dati e di creazione dell'istanza in memoria originale è detto deserializzazione.  
  
 
  
<a name="AboutSerialization"></a>   
## <a name="about-document-serialization"></a>Informazioni sulla serializzazione di documenti  
 In teoria, il processo di serializzazione e deserializzazione di un documento in memoria è trasparente per l'applicazione.  L'applicazione chiama un metodo di scrittura del serializzatore per salvare il documento, mentre un metodo di lettura del deserializzatore accede all'archivio dati e ricrea l'istanza originale in memoria.  Il formato specifico in cui vengono archiviati i dati non costituisce in genere un problema per l'applicazione, purché il processo di serializzazione e deserializzazione ricrei il documento nel formato originale.  
  
 Nelle applicazioni sono spesso disponibili varie opzioni di serializzazione che consentono all'utente di salvare i documenti in supporti o formati diversi.  Ad esempio, è possibile che in un'applicazione siano disponibili opzioni "Salva con nome" per l'archiviazione di un documento su disco, in un database o come servizio Web.  Allo stesso modo, serializzatori diversi potrebbero archiviare il documento in formati diversi quali HTML, RTF, XML, XPS o, in alternativa, in un formato di terze parti.  Per l'applicazione, la serializzazione definisce un'interfaccia che isola i dettagli del supporto di archiviazione nell'implementazione di ogni specifico serializzatore.  Oltre ai vantaggi di incapsulare dettagli di archiviazione, il [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] <xref:System.Windows.Documents.Serialization> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] forniscono altre importanti funzionalità.  
  
### <a name="features-of-net-framework-30-document-serializers"></a>Funzionalità dei serializzatori di documenti di .NET Framework 3.0  
  
-   L'accesso diretto agli oggetti documento di alto livello (albero logico e oggetti visivi) consente di archiviare in modo efficiente contenuto impaginato, elementi 2D/3D, immagini, supporti, collegamenti ipertestuali, annotazioni e altro contenuto di supporto.  
  
-   Operazioni sincrone e asincrone.  
  
-   Supporto per serializzatori plug-in con funzionalità avanzate:  
  
    -   Accesso a livello di sistema disponibile da tutte le applicazioni [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)].  
  
    -   Individuazione semplice dei plug-in dell'applicazione.  
  
    -   Facilità di distribuzione, installazione e aggiornamento per i plug-in di terze parti personalizzati.  
  
    -   Supporto dell'interfaccia utente per impostazioni e opzioni di runtime personalizzate.  
  
### <a name="xps-print-path"></a>Percorso di stampa XPS  
 Il percorso di stampa [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] di [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] assicura inoltre un meccanismo estensibile per la scrittura di documenti tramite l'output di stampa.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] funge sia da formato di file di documento che da formato nativo dello spool di stampa per documenti [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  I documenti [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] possono essere inviati direttamente alle stampanti compatibili con [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] senza la necessità di essere convertiti in un formato intermedio.  Vedere [Cenni preliminari sulla stampa](../../../../docs/framework/wpf/advanced/printing-overview.md) per altre informazioni sulle opzioni e le funzionalità dell'output del percorso di stampa.  
  
<a name="PluginSerializers"></a>   
## <a name="plug-in-serializers"></a>Serializzatori plug-in  
 Il <xref:System.Windows.Documents.Serialization> API offrono supporto per i serializzatori di plug-in e serializzatori collegati vengono installati separatamente dall'applicazione, associare in fase di esecuzione e si accede tramite il <xref:System.Windows.Documents.Serialization.SerializerProvider> meccanismo di individuazione.  I serializzatori plug-in offrono notevoli vantaggi in termini di facilità di distribuzione e uso a livello di sistema.  I serializzatori collegati possono anche essere implementati per ambienti parzialmente attendibili, ad esempio [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], in cui i serializzatori plug-in non sono accessibili.  Serializzatori collegati, si basano sull'implementazione di una derivata la <xref:System.Windows.Documents.Serialization.SerializerWriter> classe, vengono compilati e collegati direttamente nell'applicazione.  Sia i serializzatori plug-in che i serializzatori collegati funzionano tramite eventi e metodi pubblici identici che semplificano l'uso di uno o di entrambi i tipi di serializzatori nella stessa applicazione.  
  
 I serializzatori plug-in garantiscono agli sviluppatori di applicazioni estensibilità per nuovi progetti di archiviazione e formati di file, senza la necessità di scrivere direttamente codice per ogni potenziale formato in fase di compilazione.  I serializzatori plug-in sono utili anche agli sviluppatori di terze parti in quanto forniscono un metodo standardizzato per distribuire, installare e aggiornare plug-in accessibili al sistema per formati di file personalizzati o proprietari.  
  
### <a name="using-a-plug-in-serializer"></a>Uso di un serializzatore plug-in  
 I serializzatori plug-in sono semplici da usare.  Il <xref:System.Windows.Documents.Serialization.SerializerProvider> classe enumera un <xref:System.Windows.Documents.Serialization.SerializerDescriptor> dell'oggetto per ogni plug-in installato nel sistema.  Il <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> proprietà filtra il plug-in installati in base alla configurazione corrente e verifica che il serializzatore può essere caricato e utilizzato dall'applicazione.  Il <xref:System.Windows.Documents.Serialization.SerializerDescriptor> fornisce inoltre altre proprietà, ad esempio <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> e <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, che l'applicazione può utilizzare per richiedere all'utente la selezione di un serializzatore per un formato di output disponibili.  Un serializzatore plug-in predefinito per [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] viene fornito con [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] ed è sempre enumerato.  Dopo che l'utente seleziona un formato di output, il <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> metodo viene utilizzato per creare un <xref:System.Windows.Documents.Serialization.SerializerWriter> per il formato specifico.  Il <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> può quindi essere chiamato il metodo per restituire il flusso del documento nell'archivio dati.  
  
 L'esempio seguente illustra un'applicazione che utilizza il <xref:System.Windows.Documents.Serialization.SerializerProvider> metodo in una proprietà di "questa proprietà".  Questa proprietà enumera i plug-in installati e viene compilata una stringa di filtro con le opzioni di file disponibili per un <xref:Microsoft.Win32.SaveFileDialog>.  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 Dopo aver selezionato un nome di file di output dall'utente, nell'esempio seguente viene illustrato l'utilizzo del <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> metodo per archiviare un documento specificato in un formato specificato.  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### <a name="installing-plug-in-serializers"></a>Installazione di serializzatori plug-in  
 La <xref:System.Windows.Documents.Serialization.SerializerProvider> classe fornisce l'interfaccia dell'applicazione di livello superiore per l'accesso e individuazione serializzatore plug-in.  <xref:System.Windows.Documents.Serialization.SerializerProvider>Individua e fornisce all'applicazione un elenco dei serializzatori che siano installati e accessibili nel sistema.  Le specifiche dei serializzatori installati vengono definite tramite le impostazioni del Registro di sistema.  I serializzatori di plug-in è possibile aggiungere al Registro di sistema tramite il <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> metodo; o se [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] non è ancora installato, gli script di installazione di plug-in possono essere direttamente i valori del Registro di sistema di set.  Il <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> metodo può essere utilizzato per rimuovere precedentemente installato plug-in, o le impostazioni del Registro di sistema possono essere reimpostate in modo analogo uno script di disinstallazione.  
  
### <a name="creating-a-plug-in-serializer"></a>Creazione di un serializzatore plug-in  
 Sia i serializzatori plug-in che i serializzatori collegati usano gli stessi eventi e metodi pubblici esposti e possono essere progettati in modo simile per funzionare in modalità sincrona o asincrona.  Per creare un serializzatore plug-in, sono in genere necessari tre passaggi di base:  
  
1.  Implementare ed eseguire il debug del serializzatore innanzitutto come serializzatore collegato.  La creazione iniziale di un serializzatore compilato e collegato direttamente in un'applicazione di prova consente l'accesso completo ai punti di interruzione e ad altri servizi di debug utili per il test.  
  
2.  Dopo che il serializzatore è stato testato completamente, un' <xref:System.Windows.Documents.Serialization.ISerializerFactory> interfaccia viene aggiunto per creare un plug-in.  Il <xref:System.Windows.Documents.Serialization.ISerializerFactory> interfaccia consente l'accesso completo a tutti i [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] gli oggetti che includono l'albero logico, <xref:System.Windows.UIElement> oggetti, <xref:System.Windows.Documents.IDocumentPaginatorSource>, e <xref:System.Windows.Media.Visual> elementi.  È inoltre <xref:System.Windows.Documents.Serialization.ISerializerFactory> fornisce gli stessi metodi sincroni e asincroni ed eventi utilizzati dai serializzatori collegati.  Poiché l'output dei documenti di grandi dimensioni può richiedere tempo, le operazioni asincrone sono consigliate per garantire l'interazione dell'utente e fornire un'opzione "Annulla" se si verifica un problema relativo all'archivio dati.  
  
3.  Dopo la creazione del serializzatore plug-in, viene implementato uno script di installazione per la distribuzione, l'installazione e la disinstallazione del plug-in (vedere la sezione precedente "[Installazione di serializzatori plug-in](#InstallingPluginSerializers)").  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Documents.Serialization>  
 <xref:System.Windows.Xps.XpsDocumentWriter>  
 <xref:System.Windows.Xps.Packaging.XpsDocument>  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [XML Paper Specification: Overview](http://go.microsoft.com/fwlink?LinkID=106246) (Panoramica di XML Paper Specification)
