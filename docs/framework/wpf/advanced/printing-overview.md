---
title: Cenni preliminari sulla stampa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print path [WPF], XPS
- printers [WPF], XPSDrv-based
- printing [WPF]
- PrintQueue class PrintServer class [WPF]
- XML Paper Specification (XPS) file format
- XPS (XML Paper Specification) file format
- XPSDrv-based printers
- GDI print path [WPF]
ms.assetid: 0de8ac41-9aa6-413d-a121-7aa6f41539b1
ms.openlocfilehash: 902d51341850b5245b9fa6410b1954b2ab373bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187205"
---
# <a name="printing-overview"></a>Cenni preliminari sulla stampa
Con Microsoft .NET Framework, gli sviluppatori di applicazioni che utilizzano Windows Presentation Foundation (WPF) dispongono di un nuovo set completo di API di gestione del sistema di stampa e stampa. Con Windows Vista, alcuni di questi miglioramenti del sistema di stampa sono disponibili anche per gli sviluppatori che creano applicazioni Windows Form e gli sviluppatori che utilizzano codice non gestito. Alla base di questa nuova funzionalità vi sono il nuovo formato di file XML Paper Specification (XPS) e il percorso di stampa XPS.  
  
 In questo argomento sono contenute le sezioni seguenti.  
  
<a name="introduction_to_XPS"></a>
## <a name="about-xps"></a>Informazioni su XPS  
 XPS è un formato di documento elettronico, un formato di file di spool e un linguaggio di descrizione della pagina. Si tratta di un formato di documento aperto che utilizza XML, Open Packaging Conventions (OPC) e altri standard di settore per creare documenti multipiattaforma. XPS semplifica il processo di creazione, condivisione, stampa, visualizzazione e archiviazione dei documenti digitali. Per ulteriori informazioni su XPS, consultate [Documenti XPS.](/windows/desktop/printdocs/documents)  
  
 Diverse tecniche per la stampa di contenuto basato su XPS utilizzando WPFWPF sono illustrate in Stampa di [file XPS](how-to-programmatically-print-xps-files.md)a livello di codice. Può essere utile fare riferimento a tali esempi durante la lettura di questo argomento. Gli sviluppatori di codice non gestito devono consultare la documentazione relativa alla [funzione MXDC_ESCAPE](/windows/desktop/printdocs/mxdc-escape). Gli sviluppatori di Windows Form <xref:System.Drawing.Printing> devono utilizzare l'API nello spazio dei nomi che non supporta il percorso di stampa XPS completo, ma supporta un percorso di stampa ibrido da GDI a XPS. Vedere **Architettura del percorso di stampa** più avanti.  
  
<a name="XPS_print_path_intro"></a>
## <a name="xps-print-path"></a>Percorso di stampa XPS  
 Il percorso di stampa XPS (XML Paper Specification) è una nuova funzionalità di Windows che ridefinisce la modalità di gestione della stampa nelle applicazioni Windows. Poiché XPS può sostituire un linguaggio di presentazione del documento (ad esempio RTF), un formato dello spooler di stampa (ad esempio WMF) e un linguaggio di descrizione della pagina (ad esempio PCL o Postscript); il nuovo percorso di stampa mantiene il formato XPS dalla pubblicazione dell'applicazione all'elaborazione finale nel driver o nel dispositivo di stampa.  
  
 Il percorso di stampa XPS si basa sul modello di driver della stampante XPS (XPSDrv), che offre diversi vantaggi per gli sviluppatori, ad esempio "ciò che si vede è ciò che si ottiene" (WYSIWYG), il supporto del colore migliorato e le prestazioni di stampa notevolmente migliorate. Per ulteriori informazioni su XPSDrv, vedere la documentazione di [Windows Driver Kit.](/windows-hardware/drivers/)  
  
 Il funzionamento dello spooler di stampa per i documenti XPS è essenzialmente lo stesso delle versioni precedenti di Windows. Tuttavia, è stato migliorato per supportare il percorso di stampa XPS oltre al percorso di stampa GDI esistente. Il nuovo percorso di stampa utilizza in modo nativo un file di spool XPS. Mentre i driver della stampante in modalità utente scritti per le versioni precedenti di Windows continueranno a funzionare, è necessario un driver della stampante XPS (XPSDrv) per utilizzare il percorso di stampa XPS.  
  
 I vantaggi del percorso di stampa XPS sono significativi e includono:  
  
- Supporto per la stampa WYSIWYG  
  
- Supporto nativo di profili colori avanzati che includono 32 bit per canale (bpc), CMYK, colori con nome, molteplici inchiostri e supporto nativo di trasparenza e sfumature.  
  
- Miglioramento delle prestazioni di stampa per le applicazioni basate su .NET Framework e Win32.  
  
- Formato XPS standard del settore.  
  
 Per gli scenari di stampa di base, è disponibile un'API semplice e intuitiva con un unico punto di ingresso per l'interfaccia utente, la configurazione e l'invio di processi. Per scenari avanzati, è disponibile un supporto aggiuntivo per la personalizzazione dell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (o nessuna [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), la stampa sincrona o asincrona e le funzionalità di stampa in modalità batch. Entrambe le opzioni forniscono supporto di stampa in modalità di attendibilità completa o parziale.  
  
 XPS è stato progettato tenendo presente l'estendibilità. Utilizzando il framework di estendibilità, le funzionalità e le funzionalità possono essere aggiunte a XPS in modo modulare. Le funzionalità di estensibilità includono:  
  
- Schema di stampa. Lo schema pubblico viene aggiornato regolarmente e consente la rapida estensione delle funzionalità del dispositivo Vedere **PrintTicket e PrintCapabilities** più avanti.  
  
- Pipeline del filtro estensibile. La pipeline di filtro XPS Printer Driver (XPSDrv) è stata progettata per consentire la stampa diretta e scalabile di documenti XPS. Per ulteriori informazioni, vedere [Driver della stampante XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers).
  
### <a name="print-path-architecture"></a>Architettura del percorso di stampa  
 Mentre entrambe le applicazioni Win32 e .NET Framework supportano XPS, le applicazioni Win32 e Windows Form utilizzano una conversione da GDI a XPS per creare contenuto in formato XPS per il driver della stampante XPS (XPSDrv). Queste applicazioni non sono necessarie per utilizzare il percorso di stampa XPS e possono continuare a utilizzare la stampa basata su Enhanced Metafile (EMF). Tuttavia, la maggior parte delle funzionalità e dei miglioramenti XPS sono disponibili solo per le applicazioni destinate al percorso di stampa XPS.  
  
 Per consentire l'utilizzo di stampanti basate su XPSDrv da parte di applicazioni Win32 e Windows Form, il driver della stampante XPS (XPSDrv) supporta la conversione di GDI in formato XPS. Il modello XPSDrv fornisce inoltre un convertitore per il formato da XPS a GDI in modo che le applicazioni Win32 possano stampare documenti XPS. Per le applicazioni WPFWPF, la <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> conversione del formato <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> XPS <xref:System.Windows.Xps.XpsDocumentWriter> in formato GDI viene eseguita automaticamente dai metodi e della classe ogni volta che la coda di stampa di destinazione dell'operazione di scrittura non dispone di un driver XPSDrv. Le applicazioni Windows Form non possono stampare documenti XPS.  
  
 Nella figura seguente viene illustrato il sottosistema di stampa e vengono definite le parti fornite da Microsoft e le parti definite dai fornitori di software e hardware:  
  
 ![Screenshot mostra il sistema di stampa XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Stampa XPS di base  
 WPFWPF definisce un'API di base e avanzata. Per le applicazioni che non richiedono un'ampia personalizzazione della stampa o l'accesso all'intero set di funzionalità XPS, è disponibile il supporto di stampa di base. Il supporto di stampa di base viene esposto tramite un controllo finestra di dialogo di stampa che richiede una configurazione minima e offre un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] già familiare all'utente. Molte funzionalità XPS sono disponibili utilizzando questo modello di stampa semplificato.  
  
#### <a name="printdialog"></a>PrintDialog  
 Il <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> controllo fornisce un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]unico punto di ingresso per l'invio di processi XPS. Per informazioni su come creare un'istanza del controllo e come usarlo, vedere [Richiamare una finestra di dialogo di stampa](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Stampa XPS avanzata  
 Per accedere al set completo di funzionalità XPS, è necessario utilizzare l'API di stampa avanzata. Diverse API rilevanti sono descritte più dettagliatamente di seguito. Per un elenco completo delle API del percorso <xref:System.Windows.Xps> <xref:System.Printing> di stampa XPS, vedere i riferimenti allo spazio dei nomi e .  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket e PrintCapabilities  
 Le <xref:System.Printing.PrintTicket> <xref:System.Printing.PrintCapabilities> classi e sono alla base delle funzionalità XPS avanzate. Entrambi i tipi di oggetti sono strutture formattate in XML di funzionalità orientate alla stampa, ad esempio regole di confronto, stampa fronte-retro, graffatura e così via. Queste strutture sono definite dallo schema di stampa. Un oggetto <xref:System.Printing.PrintTicket> indica a una stampante come elaborare un processo di stampa. La classe <xref:System.Printing.PrintCapabilities> consente di definire le funzionalità di una stampante. Eseguendo una query delle funzionalità di una stampante, è possibile creare un oggetto <xref:System.Printing.PrintTicket> per usare in modo completo tutte le funzionalità supportate di una stampante. Analogamente, è possibile evitare le funzionalità non supportate.  
  
 L'esempio riportato di seguito illustra come eseguire una query della classe <xref:System.Printing.PrintCapabilities> di una stampante e creare un oggetto <xref:System.Printing.PrintTicket> tramite il codice.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer e PrintQueue  
 La classe <xref:System.Printing.PrintServer> rappresenta un server di stampa di rete, mentre la classe <xref:System.Printing.PrintQueue> rappresenta una stampante e la coda del processo di output a essa associata. Insieme, queste API consentono la gestione avanzata dei processi di stampa di un server. La classe <xref:System.Printing.PrintServer>, o una delle relative classi derivate, consente di gestire la classe <xref:System.Printing.PrintQueue>. Il metodo <xref:System.Printing.PrintQueue.AddJob%2A> consente di inserire un nuovo processo di stampa nella coda.  
  
 L'esempio di codice riportato di seguito illustra come creare un oggetto <xref:System.Printing.LocalPrintServer> e come accedere al relativo oggetto <xref:System.Printing.PrintQueue> predefinito tramite il codice.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 Un <xref:System.Windows.Xps.XpsDocumentWriter>oggetto , <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> con <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> i suoi numerosi metodi e <xref:System.Printing.PrintQueue>, viene utilizzato per scrivere documenti XPS in un file . Ad esempio, <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> il metodo viene utilizzato per <xref:System.Printing.PrintTicket> restituire un documento XPS e in modo sincrono. Il <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> metodo viene utilizzato per restituire <xref:System.Printing.PrintTicket> un documento XPS e in modo asincrono.  
  
 L'esempio riportato di seguito illustra come creare un oggetto <xref:System.Windows.Xps.XpsDocumentWriter> tramite codice.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 I metodi <xref:System.Printing.PrintQueue.AddJob%2A> consentono anche di stampare in diversi modi. Vedere [Stampa di file XPS a livello di codice](how-to-programmatically-print-xps-files.md). per informazioni dettagliate.  
  
<a name="GDI_Print_Path_intro"></a>
## <a name="gdi-print-path"></a>Percorso di stampa GDI  
 Mentre le applicazioni WPFWPF supportano in modo nativo il percorso di stampa XPS, le applicazioni Win32 e Windows Form possono anche sfruttare alcune funzionalità di XPS. Il driver della stampante XPS (XPSDrv) è in grado di convertire l'output basato su GDI in formato XPS. Per gli scenari avanzati, la conversione personalizzata del contenuto è supportata tramite [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-). Analogamente, le applicazioni WPFWPF possono anche restituire il <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> percorso di <xref:System.Windows.Xps.XpsDocumentWriter> stampa GDI chiamando uno dei metodi o della classe e designando una stampante non XpsDrv come coda di stampa di destinazione.  

Per le applicazioni che non richiedono funzionalità o supporto XPS, il percorso di stampa GDI corrente rimane invariato.  
  
- Per ulteriori materiale di riferimento sul percorso di stampa GDI e sulle varie opzioni di conversione XPS, vedere [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) e [XPSDrv Printer Drivers](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>
## <a name="xpsdrv-driver-model"></a>Modello di driver XPSDrv  
 Il percorso di stampa XPS migliora l'efficienza dello spooler utilizzando XPS come formato di spool di stampa nativo durante la stampa su una stampante o un driver abilitato per XPS. Il processo di spooling semplificato elimina la necessità di generare un file di spooling intermedio, ad esempio un file di dati EMF, prima che il documento venga sottoposto a spooling. Grazie a file di spool di dimensioni inferiori, il percorso di stampa XPS può ridurre il traffico di rete e migliorare le prestazioni di stampa.  
  
 EMF è un formato chiuso che rappresenta l'output dell'applicazione come una serie di chiamate in GDI per i servizi di rendering. A differenza di EMF, il formato di spool XPS rappresenta il documento effettivo senza richiedere un'ulteriore interpretazione durante l'output su un driver della stampante basato su XPS (XPSDrv). I driver possono agire direttamente sui dati nel formato. Questa funzionalità elimina le conversioni dei dati e dello spazio colore necessarie quando si utilizzano file EMF e driver di stampa basati su GDI.  
  
 Le dimensioni dei file di spooling sono in genere ridotte quando si utilizzano documenti XPS destinati a un driver della stampante XPS (XPSDrv) rispetto ai rispettivi equivalenti EMF; tuttavia, ci sono eccezioni:  
  
- Una grafica vettoriale molto complessa, a più livelli o scritta in modo inappropriato può presentare dimensioni maggiori rispetto alla relativa versione bitmap.  
  
- Per scopi di visualizzazione, i file XPS incorporano tipi di carattere del dispositivo, nonché tipi di caratteri basati sul computer. Al contrario, i file di spooling GDI non incorporano alcun tipo di carattere del dispositivo. Tuttavia, entrambi i tipi di carattere presentano sottoinsiemi (vedere di seguito) e i driver della stampante possono rimuovere i tipi di carattere del dispositivo prima di trasmettere il file alla stampante.  
  
 La riduzione delle dimensioni di spooling viene eseguita tramite molteplici meccanismi:  
  
- **Incorporamento di sottoinsiemi di tipi di carattere**. Solo i caratteri utilizzati all'interno del documento effettivo vengono memorizzati nel file XPS.  
  
- **Supporto grafico avanzato**. Il supporto nativo per le primitive di trasparenza e sfumatura evita la rasterizzazione del contenuto nel documento XPS.  
  
- **Identificazione di risorse comuni**. Le risorse usate più volte (ad esempio un'immagine che rappresenta un logo aziendale) sono considerate risorse condivise e vengono caricate solo una volta.  
  
- **Compressione zip**. Tutti i documenti XPS utilizzano la compressione zip.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [Argomenti relativi alle procedure](printing-how-to-topics.md)
- [Documenti in WPF](documents-in-wpf.md)
- [Documenti XPS](/windows/desktop/printdocs/documents)
- [Serializzazione e archiviazione di documenti](document-serialization-and-storage.md)
- [Convertitore di documenti XPS Microsoft (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
