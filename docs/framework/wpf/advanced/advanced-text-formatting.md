---
title: Formattazione del testo avanzata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1828b6ffe2d24c2bfb98b4668a9540adf5978e5f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="advanced-text-formatting"></a>Formattazione del testo avanzata
Il [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] fornisce un set affidabile di [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] di includere il testo nell'applicazione. Layout e [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], ad esempio <xref:System.Windows.Controls.TextBlock>, fornire i più comuni e gli elementi di utilizzo generale per la presentazione del testo. Disegno [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], ad esempio <xref:System.Windows.Media.GlyphRunDrawing> e <xref:System.Windows.Media.FormattedText>, forniscono un mezzo per includere il testo formattato nei disegni. Al massimo livello avanzato, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce un motore per controllare qualsiasi aspetto della presentazione del testo, ad esempio gestione degli archivi di testo, la gestione della formattazione e gestione degli oggetti incorporati di formattazione del testo estensibile.  
  
 In questo argomento viene fornita un'introduzione a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] la formattazione del testo. Si concentra sulle implementazione client e dell'utilizzo di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] motore di formattazione del testo.  
  
> [!NOTE]
>  Tutti gli esempi di codice all'interno di questo documento, vedere il [Advanced Text Formatting Sample](http://go.microsoft.com/fwlink/?LinkID=159965).  
  

  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento si presuppone che si ha familiarità con il livello più alto [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] utilizzato per la presentazione del testo. La maggior parte degli scenari utente non richiede la formattazione di testo avanzato [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] descritti in questo argomento. Per un'introduzione al testo diversi [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], vedere [documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>Formattazione del testo avanzata  
 Il layout del testo e [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controlli [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornire proprietà di formattazione che consentono di includere facilmente testo formattato nell'applicazione. Questi controlli espongono numerose proprietà per la gestione della presentazione del testo, inclusi il carattere tipografico, le dimensioni e il colore. In circostanze normali, questi controlli sono in grado di gestire la maggior parte degli scenari di presentazione del testo nell'applicazione. Tuttavia, alcuni scenari avanzati richiedono il controllo dell'archiviazione del testo e della presentazione del testo. Per questi scopi [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] offre un motore di formattazione del testo estensibile.  
  
 Le caratteristiche di formattazione di testo avanzato, vedere [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] costituiti da un testo con formattazione motore, un archivio di testo, le sequenze di testo e le proprietà di formattazione. Motore di formattazione del testo <xref:System.Windows.Media.TextFormatting.TextFormatter>, crea le righe di testo da utilizzare per la presentazione. A questo scopo, avviare il processo di formattazione di riga e la chiamata del formattatore di testo <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>. Il formattatore recupera le sequenze di testo dall'archivio di testo chiamando l'archivio <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> metodo. Il <xref:System.Windows.Media.TextFormatting.TextRun> gli oggetti vengono quindi trasformati in <xref:System.Windows.Media.TextFormatting.TextLine> oggetti dal formattatore di testo e assegnato all'applicazione per l'ispezione o la visualizzazione.  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>Uso del formattatore di testo  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>è il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] la formattazione del testo del motore e fornisce servizi per la formattazione e le righe di testo. Il formattatore di testo può gestire diversi formati di carattere del testo e stili di paragrafo e include il supporto per il layout di testo internazionale.  
  
 A differenza di una tradizionale [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], <xref:System.Windows.Media.TextFormatting.TextFormatter> interagisce con un client di layout di testo tramite un set di metodi di callback. È necessario che il client fornire un'implementazione di questi metodi di <xref:System.Windows.Media.TextFormatting.TextSource> classe. Nel diagramma seguente viene illustrata l'interazione di layout di testo tra l'applicazione client e <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagramma del client di layout di testo e TextFormatter](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Interazione tra l'applicazione e TextFormatter  
  
 Il formattatore di testo viene utilizzato per recuperare le righe di testo formattato dall'archivio di testo, che è un'implementazione di <xref:System.Windows.Media.TextFormatting.TextSource>. Questa operazione viene eseguita creando innanzitutto un'istanza del formattatore di testo utilizzando il <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> metodo. Questo metodo crea un'istanza del formattatore di testo e imposta i valori massimi di altezza e larghezza della riga. Non appena viene creata un'istanza del formattatore di testo, il processo di creazione della riga è stato avviato chiamando il <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> metodo. <xref:System.Windows.Media.TextFormatting.TextFormatter>richiama l'origine del testo per recuperare il testo e i parametri di formattazione per le sequenze di testo che formano una riga.  
  
 L'esempio seguente illustra il processo di formattazione di un archivio di testo. Il <xref:System.Windows.Media.TextFormatting.TextFormatter> oggetto viene utilizzato per recuperare le righe di testo dall'archivio di testo e quindi formattare la riga di testo per il disegno nel <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[TextFormatterExample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>Implementazione dell'archivio di testo del client  
 Quando si estende il motore di formattazione del testo, è necessario implementare e gestire tutti gli aspetti dell'archivio di testo. Non si tratta di un'attività elementare. L'archivio di testo è responsabile del rilevamento delle proprietà delle sequenze di testo, delle proprietà dei paragrafi, degli oggetti incorporati e di altri contenuti simili. Fornisce inoltre il formattatore di testo con singoli <xref:System.Windows.Media.TextFormatting.TextRun> gli oggetti a cui il formattatore utilizza per creare <xref:System.Windows.Media.TextFormatting.TextLine> oggetti.  
  
 Per gestire la virtualizzazione dell'archivio di testo, l'archivio di testo deve essere derivato da <xref:System.Windows.Media.TextFormatting.TextSource>. <xref:System.Windows.Media.TextFormatting.TextSource>definisce il metodo, che il formattatore utilizza per recuperare le sequenze di testo dall'archivio di testo. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>è il metodo utilizzato dal formattatore di testo per recuperare il testo viene eseguito usato nella formattazione delle righe. La chiamata a <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> viene eseguita ripetutamente dal formattatore di testo fino a quando non si verifica una delle condizioni seguenti:  
  
-   Oggetto <xref:System.Windows.Media.TextFormatting.TextEndOfLine> o viene restituita una sottoclasse.  
  
-   La larghezza complessiva delle sequenze di testo supera la larghezza massima della riga specificata nella chiamata per creare il formattatore di testo o la chiamata al formattatore di testo <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> metodo.  
  
-   Oggetto [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] sequenza di nuova riga, ad esempio "CF", "LF" o "CRLF", viene restituito.  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>Inserimento delle sequenze di testo  
 Il fulcro del processo di formattazione del testo è rappresentato dall'interazione tra il formattatore di testo e l'archivio di testo. L'implementazione di <xref:System.Windows.Media.TextFormatting.TextSource> fornisce il formattatore di testo con il <xref:System.Windows.Media.TextFormatting.TextRun> oggetti e le proprietà con cui si vuole formattare il testo viene eseguito. Questa interazione viene gestita dal <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> metodo, che viene chiamato dal formattatore di testo.  
  
 Nella tabella seguente vengono illustrati alcuni degli operatori <xref:System.Windows.Media.TextFormatting.TextRun> oggetti.  
  
|Tipo di TextRun|Utilizzo|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Sequenza di testo specializzata usata per passare nuovamente al formattatore di testo una rappresentazione dei glifi dei caratteri.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Sequenza di testo specializzata usata per fornire contenuto nel quale la misurazione, l'hit testing e il disegno vengono eseguite come un'unica operazione, ad esempio un pulsante o un'immagine all'interno del testo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Sequenza di testo specializzata usata per contrassegnare la fine di una riga.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Sequenza di testo specializzata usata per contrassegnare la fine di un paragrafo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Il testo specializzata utilizzata per contrassegnare la fine di un segmento, ad esempio per terminare l'ambito interessato da una precedente <xref:System.Windows.Media.TextFormatting.TextModifier> eseguire.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Sequenza di testo specializzata usata per contrassegnare un intervallo di caratteri nascosti.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Sequenza di testo specializzata usata per modificare le proprietà delle sequenze di testo nel relativo ambito. L'ambito si estende per la corrispondenza successiva <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> sequenza di testo o al successivo <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>.|  
  
 Predefiniti <xref:System.Windows.Media.TextFormatting.TextRun> oggetti possono essere sottoclassati. Ciò consente all'origine del testo di fornire al formattatore di testo sequenze di testo che includono dati personalizzati.  
  
 Nell'esempio seguente viene illustrato un <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> metodo. Questo archivio di testo restituisce <xref:System.Windows.Media.TextFormatting.TextRun> oggetti al formattatore di testo per l'elaborazione.  
  
 [!code-csharp[TextFormatterExample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
>  In questo esempio, l'archivio di testo fornisce a tutto il testo le stesse proprietà. Gli archivi di testo avanzati devono implementare una gestione personalizzata dell'estensione in modo da consentire ai singoli caratteri di avere proprietà diverse.  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>Specifica delle proprietà di formattazione  
 <xref:System.Windows.Media.TextFormatting.TextRun>gli oggetti vengono formattati utilizzando le proprietà fornite dall'archivio di testo. Queste proprietà possono essere di due tipi, <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> e <xref:System.Windows.Media.TextFormatting.TextRunProperties>. <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>gestisce le proprietà del paragrafo, ad esempio <xref:System.Windows.TextAlignment> e <xref:System.Windows.FlowDirection>. <xref:System.Windows.Media.TextFormatting.TextRunProperties>proprietà che possono essere diverse per ogni eseguito all'interno di un paragrafo, ad esempio il pennello in primo piano, il testo <xref:System.Windows.Media.Typeface>e dimensioni del carattere. Per implementare i paragrafi e testo personalizzato, eseguire i tipi di proprietà, l'applicazione deve creare classi che derivano da <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> e <xref:System.Windows.Media.TextFormatting.TextRunProperties> rispettivamente.  
  
## <a name="see-also"></a>Vedere anche  
 [Funzionalità tipografiche di WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
