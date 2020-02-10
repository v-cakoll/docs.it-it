---
title: Serializzazione e archiviazione di documenti
ms.date: 03/30/2017
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
ms.openlocfilehash: 6703825d4453b2e0e65036fa2d9c856139ee473c
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094566"
---
# <a name="document-serialization-and-storage"></a>Serializzazione e archiviazione di documenti

Microsoft .NET Framework fornisce un ambiente potente per la creazione e la visualizzazione di documenti di alta qualità.  Funzionalità avanzate che supportano sia documenti fissi che documenti di flusso, controlli di visualizzazione avanzati, combinati con potenti funzionalità grafiche 2D e 3D, .NET Framework applicazioni a un nuovo livello di qualità e esperienza utente.  La possibilità di gestire in modo flessibile una rappresentazione in memoria di un documento è una funzionalità chiave di .NET Framework e la possibilità di salvare e caricare in modo efficiente i documenti da un archivio dati è la necessità di quasi tutte le applicazioni.  Il processo di conversione di un documento da una rappresentazione in memoria interna a un archivio dati esterno è detto serializzazione.  Il processo inverso di lettura di un archivio dati e di creazione dell'istanza in memoria originale è detto deserializzazione.

<a name="AboutSerialization"></a>

## <a name="about-document-serialization"></a>Informazioni sulla serializzazione di documenti

In teoria, il processo di serializzazione e deserializzazione di un documento in memoria è trasparente per l'applicazione.  L'applicazione chiama un metodo di scrittura del serializzatore per salvare il documento, mentre un metodo di lettura del deserializzatore accede all'archivio dati e ricrea l'istanza originale in memoria.  Il formato specifico in cui vengono archiviati i dati non costituisce in genere un problema per l'applicazione, purché il processo di serializzazione e deserializzazione ricrei il documento nel formato originale.

Nelle applicazioni sono spesso disponibili varie opzioni di serializzazione che consentono all'utente di salvare i documenti in supporti o formati diversi.  Ad esempio, è possibile che in un'applicazione siano disponibili opzioni "Salva con nome" per l'archiviazione di un documento su disco, in un database o come servizio Web.  Allo stesso modo, serializzatori diversi potrebbero archiviare il documento in formati diversi quali HTML, RTF, XML, XPS o, in alternativa, in un formato di terze parti.  Per l'applicazione, la serializzazione definisce un'interfaccia che isola i dettagli del supporto di archiviazione nell'implementazione di ogni specifico serializzatore.  Oltre ai vantaggi derivanti dall'incapsulamento dei dettagli di archiviazione, le API .NET Framework <xref:System.Windows.Documents.Serialization> forniscono molte altre importanti funzionalità.

### <a name="features-of-net-framework-30-document-serializers"></a>Funzionalità dei serializzatori di documenti di .NET Framework 3.0

- L'accesso diretto agli oggetti documento di alto livello (albero logico e oggetti visivi) consente di archiviare in modo efficiente contenuto impaginato, elementi 2D/3D, immagini, supporti, collegamenti ipertestuali, annotazioni e altro contenuto di supporto.

- Operazioni sincrone e asincrone.

- Supporto per serializzatori plug-in con funzionalità avanzate:

  - Accesso a livello di sistema per l'uso da tutte le applicazioni .NET Framework.

  - Individuazione semplice dei plug-in dell'applicazione.

  - Facilità di distribuzione, installazione e aggiornamento per i plug-in di terze parti personalizzati.

  - Supporto dell'interfaccia utente per impostazioni e opzioni di runtime personalizzate.

### <a name="xps-print-path"></a>Percorso di stampa XPS

Il percorso di stampa di Microsoft .NET Framework XPS fornisce anche un meccanismo estensibile per la scrittura di documenti tramite l'output di stampa.  XPS funge sia da formato di file di documento sia dal formato nativo dello spooler di stampa per Windows Vista.  I documenti XPS possono essere inviati direttamente alle stampanti compatibili con XPS senza dover eseguire la conversione in un formato intermedio.  Vedere [Cenni preliminari sulla stampa](printing-overview.md) per altre informazioni sulle opzioni e le funzionalità dell'output del percorso di stampa.

<a name="PluginSerializers"></a>

## <a name="plug-in-serializers"></a>Serializzatori plug-in

Le API <xref:System.Windows.Documents.Serialization> forniscono supporto sia per i serializzatori plug-in che per i serializzatori collegati installati separatamente dall'applicazione, vengono associati in fase di esecuzione e sono accessibili tramite il meccanismo di individuazione <xref:System.Windows.Documents.Serialization.SerializerProvider>.  I serializzatori plug-in offrono notevoli vantaggi in termini di facilità di distribuzione e uso a livello di sistema.  I serializzatori collegati possono essere implementati anche per ambienti con attendibilità parziale, ad esempio le applicazioni browser XAML (XBAPs), in cui i serializzatori plug-in non sono accessibili.  I serializzatori collegati, basati su un'implementazione derivata della classe <xref:System.Windows.Documents.Serialization.SerializerWriter>, vengono compilati e collegati direttamente nell'applicazione.  Sia i serializzatori plug-in che i serializzatori collegati funzionano tramite eventi e metodi pubblici identici che semplificano l'uso di uno o di entrambi i tipi di serializzatori nella stessa applicazione.

I serializzatori plug-in garantiscono agli sviluppatori di applicazioni estensibilità per nuovi progetti di archiviazione e formati di file, senza la necessità di scrivere direttamente codice per ogni potenziale formato in fase di compilazione.  I serializzatori plug-in sono utili anche agli sviluppatori di terze parti in quanto forniscono un metodo standardizzato per distribuire, installare e aggiornare plug-in accessibili al sistema per formati di file personalizzati o proprietari.

### <a name="using-a-plug-in-serializer"></a>Uso di un serializzatore plug-in

I serializzatori plug-in sono semplici da usare.  La classe <xref:System.Windows.Documents.Serialization.SerializerProvider> enumera un oggetto <xref:System.Windows.Documents.Serialization.SerializerDescriptor> per ogni plug-in installato nel sistema.  La proprietà <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> filtra i plug-in installati in base alla configurazione corrente e verifica che il serializzatore possa essere caricato e utilizzato dall'applicazione.  Il <xref:System.Windows.Documents.Serialization.SerializerDescriptor> fornisce anche altre proprietà, ad esempio <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> e <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, che l'applicazione può usare per richiedere all'utente di selezionare un serializzatore per un formato di output disponibile.  Un serializzatore plug-in predefinito per XPS viene fornito con .NET Framework ed è sempre enumerato.  Quando l'utente seleziona un formato di output, viene usato il metodo <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> per creare un <xref:System.Windows.Documents.Serialization.SerializerWriter> per il formato specifico.  È quindi possibile chiamare il metodo <xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A?displayProperty=nameWithType> per restituire il flusso del documento nell'archivio dati.

Nell'esempio seguente viene illustrata un'applicazione che utilizza il metodo <xref:System.Windows.Documents.Serialization.SerializerProvider> in una proprietà "PlugInFileFilter".  PlugInFileFilter enumera i plug-in installati e compila una stringa di filtro con le opzioni del file disponibili per un <xref:Microsoft.Win32.SaveFileDialog>.

[!code-csharp[DocumentSerialize#DocSerializeFileFilter](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]

Dopo che un nome di file di output è stato selezionato dall'utente, nell'esempio seguente viene illustrato l'utilizzo del metodo <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> per archiviare un documento specificato in un formato specificato.

[!code-csharp[DocumentSerialize#DocSerializePlugIn](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]

<a name="InstallingPluginSerializers"></a>

### <a name="installing-plug-in-serializers"></a>Installazione di serializzatori plug-in

La classe <xref:System.Windows.Documents.Serialization.SerializerProvider> fornisce l'interfaccia dell'applicazione di livello superiore per l'individuazione e l'accesso del serializzatore plug-in.  <xref:System.Windows.Documents.Serialization.SerializerProvider> individua e fornisce all'applicazione un elenco dei serializzatori installati e accessibili nel sistema.  Le specifiche dei serializzatori installati vengono definite tramite le impostazioni del Registro di sistema.  I serializzatori plug-in possono essere aggiunti al registro di sistema tramite il metodo <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A>. Se .NET Framework non è ancora installato, lo script di installazione del plug-in può impostare direttamente i valori del registro di sistema.  Il metodo <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> può essere utilizzato per rimuovere un plug-in installato in precedenza oppure è possibile reimpostare le impostazioni del registro di sistema in modo analogo tramite uno script di disinstallazione.

### <a name="creating-a-plug-in-serializer"></a>Creazione di un serializzatore plug-in

Sia i serializzatori plug-in che i serializzatori collegati usano gli stessi eventi e metodi pubblici esposti e possono essere progettati in modo simile per funzionare in modalità sincrona o asincrona.  Per creare un serializzatore plug-in, sono in genere necessari tre passaggi di base:

1. Implementare ed eseguire il debug del serializzatore innanzitutto come serializzatore collegato.  La creazione iniziale di un serializzatore compilato e collegato direttamente in un'applicazione di prova consente l'accesso completo ai punti di interruzione e ad altri servizi di debug utili per il test.

2. Quando il serializzatore viene testato completamente, viene aggiunta un'interfaccia <xref:System.Windows.Documents.Serialization.ISerializerFactory> per creare un plug-in.  L'interfaccia <xref:System.Windows.Documents.Serialization.ISerializerFactory> consente l'accesso completo a tutti gli oggetti .NET Framework che includono l'albero logico, gli oggetti <xref:System.Windows.UIElement>, <xref:System.Windows.Documents.IDocumentPaginatorSource>e gli elementi <xref:System.Windows.Media.Visual>.  Inoltre <xref:System.Windows.Documents.Serialization.ISerializerFactory> fornisce gli stessi metodi ed eventi sincroni e asincroni utilizzati dai serializzatori collegati.  Poiché l'output dei documenti di grandi dimensioni può richiedere tempo, le operazioni asincrone sono consigliate per garantire l'interazione dell'utente e fornire un'opzione "Annulla" se si verifica un problema relativo all'archivio dati.

3. Dopo la creazione del serializzatore plug-in, viene implementato uno script di installazione per la distribuzione, l'installazione e la disinstallazione del plug-in (vedere la sezione precedente "[Installazione di serializzatori plug-in](#InstallingPluginSerializers)").

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Documents.Serialization>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- [Documenti in WPF](documents-in-wpf.md)
- [Panoramica della stampa](printing-overview.md)
- [XML Paper Specification](https://www.ecma-international.org/activities/XML%20Paper%20Specification/XPS%20Standard%20WD%201.6.pdf)
