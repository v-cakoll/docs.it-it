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
ms.openlocfilehash: d509de02cd1b3f645ee439c0b0eb33fd1ddbdb07
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636107"
---
# <a name="advanced-text-formatting"></a>Formattazione del testo avanzata
Windows Presentation Foundation (WPF) fornisce un set di API affidabile per includere testo nell'applicazione. Le API di layout e [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], ad esempio <xref:System.Windows.Controls.TextBlock>, forniscono gli elementi più comuni e di uso generale per la presentazione del testo. Il disegno di API, ad esempio <xref:System.Windows.Media.GlyphRunDrawing> e <xref:System.Windows.Media.FormattedText>, fornisce un mezzo per includere testo formattato nei disegni. Al livello più avanzato, WPF fornisce un motore di formattazione del testo estendibile per controllare ogni aspetto della presentazione del testo, ad esempio la gestione dell'archivio di testo, la gestione della formattazione delle esecuzioni del testo e la gestione di oggetti incorporati.  
  
 In questo argomento viene fornita un'introduzione alla formattazione del testo WPF. Si concentra sull'implementazione del client e sull'uso del motore di formattazione del testo WPF.  
  
> [!NOTE]
> Tutti gli esempi di codice all'interno di questo documento sono disponibili nell'esempio relativo alla [formattazione avanzata del testo](https://go.microsoft.com/fwlink/?LinkID=159965).  

<a name="prereq"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento presuppone che l'utente abbia familiarità con le API di livello superiore usate per la presentazione del testo. La maggior parte degli scenari utente non richiede le API avanzate di formattazione del testo illustrate in questo argomento. Per un'introduzione alle diverse API di testo, vedere [documenti in WPF](documents-in-wpf.md).  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>Formattazione del testo avanzata  
 Il layout del testo e i controlli [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in WPF forniscono le proprietà di formattazione che consentono di includere facilmente testo formattato nell'applicazione. Questi controlli espongono numerose proprietà per la gestione della presentazione del testo, inclusi il carattere tipografico, le dimensioni e il colore. In circostanze normali, questi controlli sono in grado di gestire la maggior parte degli scenari di presentazione del testo nell'applicazione. Tuttavia, alcuni scenari avanzati richiedono il controllo dell'archiviazione del testo e della presentazione del testo. WPF fornisce un motore di formattazione del testo estendibile a questo scopo.  
  
 Le funzionalità avanzate di formattazione del testo disponibili in WPF sono costituite da un motore di formattazione del testo, da un archivio di testo, da sequenze di testo e da proprietà di formattazione. Il motore di formattazione del testo <xref:System.Windows.Media.TextFormatting.TextFormatter>crea righe di testo da utilizzare per la presentazione. Questa operazione viene eseguita avviando il processo di formattazione della riga e chiamando il <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>del formattatore di testo. Il formattatore di testo recupera le esecuzioni di testo dall'archivio di testo chiamando il metodo <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> dell'archivio. Gli oggetti <xref:System.Windows.Media.TextFormatting.TextRun> vengono quindi formati in <xref:System.Windows.Media.TextFormatting.TextLine> oggetti dal formattatore di testo e assegnati all'applicazione per l'ispezione o la visualizzazione.  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>Uso del formattatore di testo  
 <xref:System.Windows.Media.TextFormatting.TextFormatter> è il motore di formattazione del testo WPF e fornisce servizi per la formattazione e l'infrazione di righe di testo. Il formattatore di testo può gestire diversi formati di carattere del testo e stili di paragrafo e include il supporto per il layout di testo internazionale.  
  
 Diversamente da un'API di testo tradizionale, il <xref:System.Windows.Media.TextFormatting.TextFormatter> interagisce con un client di layout di testo tramite un set di metodi di callback. Richiede che il client fornisca questi metodi in un'implementazione della classe <xref:System.Windows.Media.TextFormatting.TextSource>. Nel diagramma seguente viene illustrata l'interazione del layout del testo tra l'applicazione client e <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagramma del client del layout di testo e TextFormatter](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 Il formattatore di testo viene utilizzato per recuperare le righe di testo formattato dall'archivio di testo, che è un'implementazione di <xref:System.Windows.Media.TextFormatting.TextSource>. Questa operazione viene eseguita creando prima un'istanza del formattatore di testo utilizzando il metodo <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A>. Questo metodo crea un'istanza del formattatore di testo e imposta i valori massimi di altezza e larghezza della riga. Non appena viene creata un'istanza del formattatore di testo, il processo di creazione della riga viene avviato chiamando il metodo <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>. <xref:System.Windows.Media.TextFormatting.TextFormatter> richiama l'origine del testo per recuperare il testo e i parametri di formattazione per le esecuzioni del testo che formano una riga.  
  
 L'esempio seguente illustra il processo di formattazione di un archivio di testo. L'oggetto <xref:System.Windows.Media.TextFormatting.TextFormatter> viene utilizzato per recuperare righe di testo dall'archivio di testo e quindi formattare la riga di testo per il disegno nel <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>Implementazione dell'archivio di testo del client  
 Quando si estende il motore di formattazione del testo, è necessario implementare e gestire tutti gli aspetti dell'archivio di testo. Non si tratta di un'attività elementare. L'archivio di testo è responsabile del rilevamento delle proprietà delle sequenze di testo, delle proprietà dei paragrafi, degli oggetti incorporati e di altri contenuti simili. Fornisce anche il formattatore di testo con singoli oggetti <xref:System.Windows.Media.TextFormatting.TextRun> che il formattatore di testo usa per creare <xref:System.Windows.Media.TextFormatting.TextLine> oggetti.  
  
 Per gestire la virtualizzazione dell'archivio di testo, l'archivio di testo deve essere derivato da <xref:System.Windows.Media.TextFormatting.TextSource>. <xref:System.Windows.Media.TextFormatting.TextSource> definisce il metodo usato dal formattatore di testo per recuperare le sequenze di testo dall'archivio di testo. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> è il metodo utilizzato dal formattatore di testo per recuperare le esecuzioni di testo utilizzate nella formattazione della riga. La chiamata a <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> viene eseguita ripetutamente dal formattatore di testo fino a quando non si verifica una delle condizioni seguenti:  
  
- Viene restituito un <xref:System.Windows.Media.TextFormatting.TextEndOfLine> o una sottoclasse.  
  
- La larghezza accumulata delle esecuzioni di testo supera la lunghezza massima consentita nella chiamata per creare il formattatore di testo o la chiamata al metodo <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> del formattatore di testo.  
  
- Viene restituita una sequenza di nuova riga Unicode, ad esempio "CF", "LF" o "CRLF".  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>Inserimento delle sequenze di testo  
 Il fulcro del processo di formattazione del testo è rappresentato dall'interazione tra il formattatore di testo e l'archivio di testo. L'implementazione di <xref:System.Windows.Media.TextFormatting.TextSource> fornisce il formattatore di testo con gli oggetti di <xref:System.Windows.Media.TextFormatting.TextRun> e le proprietà con le quali formattare le esecuzioni di testo. Questa interazione viene gestita dal metodo <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>, che viene chiamato dal formattatore di testo.  
  
 Nella tabella seguente vengono illustrati alcuni degli oggetti <xref:System.Windows.Media.TextFormatting.TextRun> predefiniti.  
  
|Tipo di TextRun|Usage|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Sequenza di testo specializzata usata per passare nuovamente al formattatore di testo una rappresentazione dei glifi dei caratteri.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Sequenza di testo specializzata usata per fornire contenuto nel quale la misurazione, l'hit testing e il disegno vengono eseguite come un'unica operazione, ad esempio un pulsante o un'immagine all'interno del testo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Sequenza di testo specializzata usata per contrassegnare la fine di una riga.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Sequenza di testo specializzata usata per contrassegnare la fine di un paragrafo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Sequenza di testo specializzata usata per contrassegnare la fine di un segmento, ad esempio per terminare l'ambito interessato da un'esecuzione <xref:System.Windows.Media.TextFormatting.TextModifier> precedente.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Sequenza di testo specializzata usata per contrassegnare un intervallo di caratteri nascosti.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Sequenza di testo specializzata usata per modificare le proprietà delle sequenze di testo nel relativo ambito. L'ambito si estende alla successiva sequenza di testo <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> corrispondente o al <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>successivo.|  
  
 Uno degli oggetti <xref:System.Windows.Media.TextFormatting.TextRun> predefiniti può essere sottoclassato. Ciò consente all'origine del testo di fornire al formattatore di testo sequenze di testo che includono dati personalizzati.  
  
 Nell'esempio seguente viene illustrato un metodo <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>. Questo archivio di testo restituisce <xref:System.Windows.Media.TextFormatting.TextRun> oggetti al formattatore di testo per l'elaborazione.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> In questo esempio, l'archivio di testo fornisce a tutto il testo le stesse proprietà. Gli archivi di testo avanzati devono implementare una gestione personalizzata dell'estensione in modo da consentire ai singoli caratteri di avere proprietà diverse.  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>Specifica delle proprietà di formattazione  
 gli oggetti <xref:System.Windows.Media.TextFormatting.TextRun> vengono formattati usando le proprietà fornite dall'archivio di testo. Queste proprietà sono disponibili in due tipi, <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> e <xref:System.Windows.Media.TextFormatting.TextRunProperties>. <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> gestire le proprietà inclusivi di paragrafo, ad esempio <xref:System.Windows.TextAlignment> e <xref:System.Windows.FlowDirection>. <xref:System.Windows.Media.TextFormatting.TextRunProperties> sono proprietà che possono essere diverse per ogni sequenza di testo all'interno di un paragrafo, ad esempio il pennello in primo piano, <xref:System.Windows.Media.Typeface>e le dimensioni del carattere. Per implementare il paragrafo personalizzato e i tipi di proprietà della sequenza di testo personalizzata, l'applicazione deve creare classi che derivano rispettivamente da <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> e <xref:System.Windows.Media.TextFormatting.TextRunProperties>.  
  
## <a name="see-also"></a>Vedere anche

- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Documenti in WPF](documents-in-wpf.md)
