---
title: Formattazione del testo avanzata
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
ms.openlocfilehash: 745d20e0bd4f877f9d4559f9fc7829b56689d35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185933"
---
# <a name="advanced-text-formatting"></a>Formattazione del testo avanzata
Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) fornisce un set affidabile di API per l'inclusione di testo nell'applicazione. Layout [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] e API, ad <xref:System.Windows.Controls.TextBlock>esempio , forniscono gli elementi più comuni e di uso generale per la presentazione di testo. Le API di disegno, ad esempio <xref:System.Windows.Media.GlyphRunDrawing> e <xref:System.Windows.Media.FormattedText>, consentono di includere testo formattato nei disegni. Al livello più avanzato, WPFWPF fornisce un motore di formattazione del testo estensibile per controllare ogni aspetto della presentazione di testo, ad esempio la gestione dell'archivio di testo, la gestione della formattazione delle constee di testo e la gestione degli oggetti incorporati.  
  
 In questo argomento viene fornita un'introduzione alla formattazione del testo WPFWPF. Si concentra sull'implementazione client e sull'utilizzo del motore di formattazione del testo WPFWPF.  
  
> [!NOTE]
> Tutti gli esempi di codice all'interno di questo documento sono disponibili [nell'esempio avanzato](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI/TextFormatting)di formattazione del testo .  

<a name="prereq"></a>
## <a name="prerequisites"></a>Prerequisites  
 Questo argomento presuppone che l'utente abbia familiarità con le API di livello superiore usate per la presentazione di testo. La maggior parte degli scenari utente non richiede le API avanzate di formattazione del testo descritte in questo argomento. Per un'introduzione alle diverse API di testo, vedere [Documenti in WPF.](documents-in-wpf.md)  
  
<a name="section1"></a>
## <a name="advanced-text-formatting"></a>Formattazione del testo avanzata  
 Il layout [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di testo e i controlli in WPFWPF forniscono proprietà di formattazione che consentono di includere facilmente testo formattato nell'applicazione. Questi controlli espongono numerose proprietà per la gestione della presentazione del testo, inclusi il carattere tipografico, le dimensioni e il colore. In circostanze normali, questi controlli sono in grado di gestire la maggior parte degli scenari di presentazione del testo nell'applicazione. Tuttavia, alcuni scenari avanzati richiedono il controllo dell'archiviazione del testo e della presentazione del testo. WPFWPF fornisce un motore di formattazione del testo estensibile per questo scopo.  
  
 Le funzionalità avanzate di formattazione del testo disponibili in WPFWPF sono costituite da un motore di formattazione del testo, un archivio di testo, sequenze di testo e proprietà di formattazione. Il motore di <xref:System.Windows.Media.TextFormatting.TextFormatter>formattazione del testo, , crea righe di testo da utilizzare per la presentazione. Ciò si ottiene initando il processo di formattazione <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>della riga e chiamando il formattatore di testo. Il formattatore di testo recupera le sequenze di <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> testo dall'archivio di testo chiamando il metodo dell'archivio. Gli <xref:System.Windows.Media.TextFormatting.TextRun> oggetti vengono <xref:System.Windows.Media.TextFormatting.TextLine> quindi formati in oggetti dal formattatore di testo e dati all'applicazione per l'ispezione o la visualizzazione.  
  
<a name="section2"></a>
## <a name="using-the-text-formatter"></a>Uso del formattatore di testo  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>è il motore di formattazione del testo WPFWPF e fornisce servizi per la formattazione e l'interruzione delle righe di testo. Il formattatore di testo può gestire diversi formati di carattere del testo e stili di paragrafo e include il supporto per il layout di testo internazionale.  
  
 A differenza di un'API di testo tradizionale, l'interagiva <xref:System.Windows.Media.TextFormatting.TextFormatter> con un client di layout di testo tramite un set di metodi di callback. Richiede al client di fornire questi metodi <xref:System.Windows.Media.TextFormatting.TextSource> in un'implementazione della classe. Nel diagramma seguente viene illustrata l'interazione del layout di testo tra l'applicazione client e <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagramma del client del layout di testo e TextFormatter](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 Il formattatore di testo viene utilizzato per recuperare righe di <xref:System.Windows.Media.TextFormatting.TextSource>testo formattate dall'archivio di testo, che è un'implementazione di . Questa operazione viene eseguita creando innanzitutto un'istanza del formattatore di testo utilizzando il <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> metodo . Questo metodo crea un'istanza del formattatore di testo e imposta i valori massimi di altezza e larghezza della riga. Non appena viene creata un'istanza del formattatore di testo, <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> il processo di creazione della riga viene avviato chiamando il metodo . <xref:System.Windows.Media.TextFormatting.TextFormatter>richiama l'origine del testo per recuperare il testo e i parametri di formattazione per le sequenze di testo che formano una linea.  
  
 L'esempio seguente illustra il processo di formattazione di un archivio di testo. L'oggetto <xref:System.Windows.Media.TextFormatting.TextFormatter> viene utilizzato per recuperare le linee di testo dall'archivio di testo e quindi formattare la linea di testo per il <xref:System.Windows.Media.DrawingContext>disegno in .  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>
## <a name="implementing-the-client-text-store"></a>Implementazione dell'archivio di testo del client  
 Quando si estende il motore di formattazione del testo, è necessario implementare e gestire tutti gli aspetti dell'archivio di testo. Non si tratta di un'attività elementare. L'archivio di testo è responsabile del rilevamento delle proprietà delle sequenze di testo, delle proprietà dei paragrafi, degli oggetti incorporati e di altri contenuti simili. Fornisce inoltre il formattatore <xref:System.Windows.Media.TextFormatting.TextRun> di testo con singoli <xref:System.Windows.Media.TextFormatting.TextLine> oggetti che il formattatore di testo utilizza per creare oggetti.  
  
 Per gestire la virtualizzazione dell'archivio di testo, <xref:System.Windows.Media.TextFormatting.TextSource>l'archivio di testo deve essere derivato da . <xref:System.Windows.Media.TextFormatting.TextSource>definisce il metodo utilizzato dal formattatore di testo per recuperare le sequenze di testo dall'archivio di testo. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>è il metodo utilizzato dal formattatore di testo per recuperare le sequenze di testo utilizzate nella formattazione della riga. La chiamata <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> a viene ripetutamente effettuata dal formattatore di testo fino a quando non si verifica una delle seguenti condizioni:  
  
- Viene <xref:System.Windows.Media.TextFormatting.TextEndOfLine> restituita un'o una sottoclasse.  
  
- La larghezza accumulata delle sequenze di testo supera la larghezza massima della riga specificata nella chiamata <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> per creare il formattatore di testo o la chiamata al metodo del formattatore di testo.  
  
- Viene restituita una sequenza di nuova riga Unicode, ad esempio "CF", "LF" o "CRLF".  
  
<a name="section4"></a>
## <a name="providing-text-runs"></a>Inserimento delle sequenze di testo  
 Il fulcro del processo di formattazione del testo è rappresentato dall'interazione tra il formattatore di testo e l'archivio di testo. L'implementazione di fornisce il <xref:System.Windows.Media.TextFormatting.TextRun> formattatore di testo con gli oggetti e le proprietà con cui formattare le sequenze di <xref:System.Windows.Media.TextFormatting.TextSource> testo. Questa interazione viene <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> gestita dal metodo , che viene chiamato dal formattatore di testo.  
  
 Nella tabella seguente vengono illustrati <xref:System.Windows.Media.TextFormatting.TextRun> alcuni degli oggetti predefiniti.  
  
|Tipo di TextRun|Uso|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Sequenza di testo specializzata usata per passare nuovamente al formattatore di testo una rappresentazione dei glifi dei caratteri.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Sequenza di testo specializzata usata per fornire contenuto nel quale la misurazione, l'hit testing e il disegno vengono eseguite come un'unica operazione, ad esempio un pulsante o un'immagine all'interno del testo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Sequenza di testo specializzata usata per contrassegnare la fine di una riga.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Sequenza di testo specializzata usata per contrassegnare la fine di un paragrafo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|La sequenza di testo specializzata utilizzata per contrassegnare la fine <xref:System.Windows.Media.TextFormatting.TextModifier> di un segmento, ad esempio per terminare l'ambito interessato da un'esecuzione precedente.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Sequenza di testo specializzata usata per contrassegnare un intervallo di caratteri nascosti.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Sequenza di testo specializzata usata per modificare le proprietà delle sequenze di testo nel relativo ambito. L'ambito si estende <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> alla successiva query <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>di testo corrispondente o alla successiva .|  
  
 Tutti gli oggetti <xref:System.Windows.Media.TextFormatting.TextRun> predefiniti possono essere sottoclassati. Ciò consente all'origine del testo di fornire al formattatore di testo sequenze di testo che includono dati personalizzati.  
  
 Nell'esempio seguente <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> viene illustrato un metodo. Questo archivio <xref:System.Windows.Media.TextFormatting.TextRun> di testo restituisce gli oggetti al formattatore di testo per l'elaborazione.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> In questo esempio, l'archivio di testo fornisce a tutto il testo le stesse proprietà. Gli archivi di testo avanzati devono implementare una gestione personalizzata dell'estensione in modo da consentire ai singoli caratteri di avere proprietà diverse.  
  
<a name="section5"></a>
## <a name="specifying-formatting-properties"></a>Specifica delle proprietà di formattazione  
 <xref:System.Windows.Media.TextFormatting.TextRun>gli oggetti vengono formattati utilizzando le proprietà fornite dall'archivio di testo. Queste proprietà sono disponibili <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> <xref:System.Windows.Media.TextFormatting.TextRunProperties>in due tipi e . <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>gestire le proprietà <xref:System.Windows.TextAlignment> inclusive <xref:System.Windows.FlowDirection>di paragrafo, ad esempio e . <xref:System.Windows.Media.TextFormatting.TextRunProperties>sono proprietà che possono essere diverse per ogni concorso <xref:System.Windows.Media.Typeface>di testo all'interno di un paragrafo, ad esempio il pennello in primo piano, e la dimensione del carattere. Per implementare tipi di proprietà di paragrafo e di <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> <xref:System.Windows.Media.TextFormatting.TextRunProperties> esecuzione di testo personalizzati, l'applicazione deve creare classi che derivano da e rispettivamente.  
  
## <a name="see-also"></a>Vedere anche

- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Documenti in WPF](documents-in-wpf.md)
