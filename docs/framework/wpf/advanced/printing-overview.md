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
ms.openlocfilehash: 3f99b0e93e6b16ac66f6869c284c1119ddfc3751
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740313"
---
# <a name="printing-overview"></a>Cenni preliminari sulla stampa
Con Microsoft .NET Framework, gli sviluppatori di applicazioni che usano Windows Presentation Foundation (WPF) dispongono di un nuovo set completo di API di gestione del sistema di stampa e stampa. Con Windows Vista, alcuni di questi miglioramenti apportati al sistema di stampa sono disponibili anche per gli sviluppatori che creano applicazioni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e sviluppatori che usano codice non gestito. Alla base di questa nuova funzionalità si trova il nuovo formato di file XPS (XML Paper Specification) e il percorso di stampa XPS.  
  
 In questo argomento sono contenute le seguenti sezioni.  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>Informazioni su XPS  
 XPS è un formato di documento elettronico, un formato di file di spooling e un linguaggio di descrizione della pagina. Si tratta di un formato di documento aperto che usa XML, Open Packaging Conventions (OPC) e altri standard del settore per creare documenti multipiattaforma. XPS semplifica il processo di creazione, condivisione, stampa, visualizzazione e archiviazione di documenti digitali. Per ulteriori informazioni su XPS, vedere la pagina relativa ai [documenti XPS](/windows/desktop/printdocs/documents).  
  
 Diverse tecniche per la stampa di contenuto basato su XPS mediante WPF sono illustrate in [stampa di file XPS a livello di codice](how-to-programmatically-print-xps-files.md). Può essere utile fare riferimento a tali esempi durante la lettura di questo argomento. Gli sviluppatori di codice non gestito dovrebbero vedere la documentazione per la [funzione MXDC_ESCAPE](/windows/desktop/printdocs/mxdc-escape). Windows Forms gli sviluppatori devono usare l'API nello spazio dei nomi <xref:System.Drawing.Printing> che non supporta il percorso di stampa XPS completo, ma supporta un percorso di stampa GDI-XPS ibrido. Vedere **Architettura del percorso di stampa** più avanti.  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>Percorso di stampa XPS  
 Il percorso di stampa XPS (XML Paper Specification) è una nuova funzionalità di Windows che consente di ridefinire il modo in cui la stampa viene gestita nelle applicazioni Windows. Poiché XPS può sostituire un linguaggio di presentazione del documento, ad esempio RTF, un formato dello spooler di stampa, ad esempio WMF, e un linguaggio di descrizione della pagina (ad esempio, PCL o PostScript); il nuovo percorso di stampa mantiene il formato XPS dalla pubblicazione dell'applicazione all'elaborazione finale nel dispositivo o nel driver di stampa.  
  
 Il percorso di stampa XPS è basato sul modello di driver della stampante XPS (XPSDrv), che offre diversi vantaggi per gli sviluppatori, ad esempio la stampa WYSIWYG, il supporto dei colori migliorato e prestazioni di stampa significativamente migliorate. Per ulteriori informazioni su XPSDrv, vedere la [documentazione di Windows Driver Kit](/windows-hardware/drivers/).  
  
 Il funzionamento dello spooler di stampa per i documenti XPS è sostanzialmente identico a quello delle versioni precedenti di Windows. Tuttavia, è stato migliorato per supportare il percorso di stampa XPS oltre al percorso di stampa GDI esistente. Il nuovo percorso di stampa USA a livello nativo un file di spooling XPS. Mentre i driver della stampante in modalità utente scritti per le versioni precedenti di Windows continueranno a funzionare, è necessario un driver della stampante XPS (XPSDrv) per usare il percorso di stampa XPS.  
  
 I vantaggi del percorso di stampa XPS sono significativi e includono:  
  
- Supporto per la stampa WYSIWYG  
  
- Supporto nativo di profili colori avanzati che includono 32 bit per canale (bpc), CMYK, colori con nome, molteplici inchiostri e supporto nativo di trasparenza e sfumature.  
  
- Prestazioni di stampa migliorate per applicazioni .NET Framework e basate su Win32.  
  
- Formato XPS standard di settore.  
  
 Per gli scenari di stampa di base, è disponibile un'API semplice e intuitiva con un unico punto di ingresso per l'interfaccia utente, la configurazione e l'invio di processi. Per scenari avanzati, è disponibile un supporto aggiuntivo per la personalizzazione dell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (o nessuna [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), la stampa sincrona o asincrona e le funzionalità di stampa in modalità batch. Entrambe le opzioni forniscono supporto di stampa in modalità di attendibilità completa o parziale.  
  
 XPS è stato progettato tenendo presente l'estensibilità. Usando il Framework di estendibilità, le funzionalità e le funzionalità possono essere aggiunte a XPS in modo modulare. Le funzionalità di estensibilità includono:  
  
- Schema di stampa. Lo schema pubblico viene aggiornato regolarmente e consente la rapida estensione delle funzionalità del dispositivo Vedere **PrintTicket e PrintCapabilities** più avanti.  
  
- Pipeline del filtro estensibile. La pipeline del filtro del driver della stampante XPS (XPSDrv) è stata progettata per consentire la stampa diretta e scalabile di documenti XPS. Per ulteriori informazioni, vedere [driver della stampante XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Architettura del percorso di stampa  
 Anche se le applicazioni Win32 e .NET Framework supportano XPS, le applicazioni Win32 e Windows Forms utilizzano una conversione da GDI a XPS per creare contenuto formattato XPS per XPS Printer driver (XPSDrv). Queste applicazioni non sono necessarie per usare il percorso di stampa XPS e possono continuare a usare la stampa basata su Enhanced Metafile (EMF). Tuttavia, la maggior parte delle funzionalità e dei miglioramenti di XPS è disponibile solo per le applicazioni destinate al percorso di stampa XPS.  
  
 Per consentire l'utilizzo di stampanti basate su XPSDrv da parte di applicazioni Win32 e Windows Forms, il driver della stampante XPS (XPSDrv) supporta la conversione del formato GDI in XPS. Il modello XPSDrv fornisce inoltre un convertitore per XPS al formato GDI, in modo che le applicazioni Win32 possano stampare documenti XPS. Per le applicazioni WPF, la conversione di XPS in formato GDI viene eseguita automaticamente dai metodi <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> della classe <xref:System.Windows.Xps.XpsDocumentWriter> ogni volta che la coda di stampa di destinazione dell'operazione di scrittura non dispone di un driver XPSDrv. (Windows Forms le applicazioni non possono stampare documenti XPS).  
  
 Nella figura seguente viene illustrato il sottosistema di stampa e vengono definite le parti fornite da Microsoft e le parti definite dai fornitori di software e hardware:  
  
 ![Screenshot che mostra il sistema di stampa XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Stampa XPS di base  
 WPF definisce un'API di base e avanzata. Per le applicazioni che non richiedono una personalizzazione di stampa estesa o l'accesso al set di funzionalità XPS completo, è disponibile il supporto di stampa di base. Il supporto di stampa di base viene esposto tramite un controllo finestra di dialogo di stampa che richiede una configurazione minima e offre un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] già familiare all'utente. Molte funzionalità XPS sono disponibili tramite questo modello di stampa semplificato.  
  
#### <a name="printdialog"></a>PrintDialog  
 Il controllo <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> fornisce un singolo punto di ingresso per [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configurazione e invio di processi XPS. Per informazioni su come creare un'istanza del controllo e come usarlo, vedere [Richiamare una finestra di dialogo di stampa](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Stampa XPS avanzata  
 Per accedere al set completo di funzionalità XPS, è necessario usare l'API di stampa avanzata. Diverse API pertinenti sono descritte in dettaglio più avanti. Per un elenco completo delle API del percorso di stampa XPS, vedere i riferimenti agli spazi dei nomi <xref:System.Windows.Xps> e <xref:System.Printing>.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket e PrintCapabilities  
 Le classi <xref:System.Printing.PrintTicket> e <xref:System.Printing.PrintCapabilities> sono le fondamenta delle funzionalità avanzate di XPS. Entrambi i tipi di oggetti sono strutture in formato XML di funzionalità orientate alla stampa, ad esempio regole di confronto, stampa su due lati, graffatura e così via. Queste strutture sono definite dallo schema di stampa. Un oggetto <xref:System.Printing.PrintTicket> indica a una stampante come elaborare un processo di stampa. La classe <xref:System.Printing.PrintCapabilities> consente di definire le funzionalità di una stampante. Eseguendo una query delle funzionalità di una stampante, è possibile creare un oggetto <xref:System.Printing.PrintTicket> per usare in modo completo tutte le funzionalità supportate di una stampante. Analogamente, è possibile evitare le funzionalità non supportate.  
  
 L'esempio riportato di seguito illustra come eseguire una query della classe <xref:System.Printing.PrintCapabilities> di una stampante e creare un oggetto <xref:System.Printing.PrintTicket> tramite il codice.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer e PrintQueue  
 La classe <xref:System.Printing.PrintServer> rappresenta un server di stampa di rete, mentre la classe <xref:System.Printing.PrintQueue> rappresenta una stampante e la coda del processo di output a essa associata. Insieme, queste API consentono una gestione avanzata dei processi di stampa di un server. La classe <xref:System.Printing.PrintServer>, o una delle relative classi derivate, consente di gestire la classe <xref:System.Printing.PrintQueue>. Il metodo <xref:System.Printing.PrintQueue.AddJob%2A> consente di inserire un nuovo processo di stampa nella coda.  
  
 L'esempio di codice riportato di seguito illustra come creare un oggetto <xref:System.Printing.LocalPrintServer> e come accedere al relativo oggetto <xref:System.Printing.PrintQueue> predefinito tramite il codice.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 Una <xref:System.Windows.Xps.XpsDocumentWriter>, con molti metodi <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>, viene utilizzata per scrivere documenti XPS in un <xref:System.Printing.PrintQueue>. Ad esempio, il metodo <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> viene utilizzato per restituire un documento XPS e <xref:System.Printing.PrintTicket> in modo sincrono. Il metodo <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> viene utilizzato per restituire un documento XPS e <xref:System.Printing.PrintTicket> in modo asincrono.  
  
 L'esempio riportato di seguito illustra come creare un oggetto <xref:System.Windows.Xps.XpsDocumentWriter> tramite codice.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 I metodi <xref:System.Printing.PrintQueue.AddJob%2A> consentono anche di stampare in diversi modi. Vedere [Stampa di file XPS a livello di codice](how-to-programmatically-print-xps-files.md). per informazioni dettagliate.  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>Percorso di stampa GDI  
 Sebbene le applicazioni WPF supportino in modo nativo il percorso di stampa XPS, le applicazioni Win32 e Windows Forms possono avvalersi anche di alcune funzionalità XPS. Il driver della stampante XPS (XPSDrv) può convertire l'output basato su GDI in formato XPS. Per gli scenari avanzati, la conversione personalizzata del contenuto è supportata tramite [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-). Analogamente, le applicazioni WPF possono anche restituire il percorso di stampa GDI chiamando uno dei metodi <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> o <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> della classe <xref:System.Windows.Xps.XpsDocumentWriter> e designando una stampante non XpsDrv come coda di stampa di destinazione.  

Per le applicazioni che non richiedono funzionalità o supporto XPS, il percorso di stampa GDI corrente rimane invariato.  
  
- Per materiale di riferimento aggiuntivo sul percorso di stampa GDI e sulle varie opzioni di conversione XPS, vedere [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) e i [driver della stampante XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>Modello di driver XPSDrv  
 Il percorso di stampa XPS migliora l'efficienza dello spooler utilizzando XPS come formato dello spooler di stampa nativo per la stampa su un driver o una stampante abilitata per XPS. Il processo di spooling semplificato elimina la necessità di generare un file di spool intermedio, ad esempio un file di dati EMF, prima dello spooling del documento. Grazie alle dimensioni del file di spool più piccolo, il percorso di stampa XPS può ridurre il traffico di rete e migliorare le prestazioni di stampa.  
  
 EMF è un formato chiuso che rappresenta l'output dell'applicazione come una serie di chiamate in GDI per i servizi di rendering. Diversamente da EMF, il formato di spooling XPS rappresenta il documento effettivo senza richiedere un'ulteriore interpretazione quando viene restituito un driver della stampante basato su XPS (XPSDrv). I driver possono agire direttamente sui dati nel formato. Questa funzionalità Elimina le conversioni dei dati e dello spazio colori necessarie quando si usano i file EMF e i driver di stampa basati su GDI.  
  
 Le dimensioni dei file di spooling vengono in genere ridotte quando si utilizzano documenti XPS destinati a un driver della stampante XPS (XPSDrv) rispetto ai rispettivi equivalenti EMF; Esistono tuttavia alcune eccezioni:  
  
- Una grafica vettoriale molto complessa, a più livelli o scritta in modo inappropriato può presentare dimensioni maggiori rispetto alla relativa versione bitmap.  
  
- Per scopi di visualizzazione, i file XPS incorporano tipi di carattere del dispositivo, nonché tipi di caratteri basati sul computer. Al contrario, i file di spooling GDI non incorporano alcun tipo di carattere del dispositivo. Tuttavia, entrambi i tipi di carattere presentano sottoinsiemi (vedere di seguito) e i driver della stampante possono rimuovere i tipi di carattere del dispositivo prima di trasmettere il file alla stampante.  
  
 La riduzione delle dimensioni di spooling viene eseguita tramite molteplici meccanismi:  
  
- **Incorporamento di sottoinsiemi di tipi di carattere**. Solo i caratteri usati nel documento effettivo vengono archiviati nel file XPS.  
  
- **Supporto grafico avanzato**. Il supporto nativo per le primitive di trasparenza e sfumatura evita la rasterizzazione del contenuto nel documento XPS.  
  
- **Identificazione di risorse comuni**. Le risorse usate più volte (ad esempio un'immagine che rappresenta un logo aziendale) sono considerate risorse condivise e vengono caricate solo una volta.  
  
- **Compressione ZIP**. Tutti i documenti XPS utilizzano la compressione ZIP.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [Procedure relative alle proprietà](printing-how-to-topics.md)
- [Documenti in WPF](documents-in-wpf.md)
- [Documenti XPS](/windows/desktop/printdocs/documents)
- [Serializzazione e archiviazione di documenti](document-serialization-and-storage.md)
- [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
