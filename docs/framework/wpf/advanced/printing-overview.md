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
ms.openlocfilehash: bb3737ca879f3687b25b021348da0c50f663c58e
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238675"
---
# <a name="printing-overview"></a>Cenni preliminari sulla stampa
Con Microsoft .NET Framework, gli sviluppatori di applicazioni con Windows Presentation Foundation (WPF) dispongono di molteplici nuove della stampa e stampare le API di gestione del sistema. Con [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], alcuni dei miglioramenti apportati al sistema di stampa sono anche disponibili agli sviluppatori che creano applicazioni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e a quelli che usano codice non gestito. Questa nuova funzionalità è basata sul nuovo formato di file [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] e sul percorso di stampa [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>Informazioni su XPS  
 Stored procedure estese è un formato di documento elettronico, un formato di file di spooling e un linguaggio di descrizione della pagina. Si tratta di un formato di documento aperto basato sull'uso di [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], [!INCLUDE[TLA#tla_opc](../../../../includes/tlasharptla-opc-md.md)] e di altri standard del settore per creare documenti per più piattaforme. Stored procedure estese semplifica il processo mediante il quale documenti digitali vengono creati, condiviso, stampati, visualizzati e archiviati. Per altre informazioni sulla stored procedure estese, vedere [documenti XPS](/windows/desktop/printdocs/documents).  
  
 Varie tecniche di stampa XPS in base al contenuto mediante [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sono illustrati nelle [a livello di codice stampa di file XPS](how-to-programmatically-print-xps-files.md). Può essere utile fare riferimento a tali esempi durante la lettura di questo argomento. (Gli sviluppatori di codice non gestito dovrebbero riscontrare documentazione per il [funzione MXDC_ESCAPE](/windows/desktop/printdocs/mxdc-escape). Gli sviluppatori di Windows Form devono usare l'API dei <xref:System.Drawing.Printing> dello spazio dei nomi che non supporta la versione completa [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] percorso di stampa, ma supporta un percorso di stampa GDI-XPS ibrido. Vedere **Architettura del percorso di stampa** più avanti.  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>Percorso di stampa XPS  
 Il percorso di stampa XML Paper Specification (XPS) è un nuovo [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] funzionalità che ridefinisce la gestione della stampa nelle applicazioni di Windows. Poiché [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] può sostituire un linguaggio di presentazione del documento (ad esempio RTF), un formato di spooler di stampa (ad esempio WMF) e un linguaggio di descrizione pagina (ad esempio PCL o Postscript), il nuovo percorso di stampa mantiene il formato XPS dalla pubblicazione dell'applicazione per il elaborazione finale nel dispositivo o driver di stampa.  
  
 Il percorso di stampa XPS è basato il modello di driver della stampante XPS (XPSDrv), offre numerosi vantaggi per gli sviluppatori, ad esempio [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] stampa, supporto del colore migliorato e prestazioni di stampa migliorate in modo significativo. (Per altre informazioni su Psdrv, vedere la [documentazione di Windows Driver Kit](/windows-hardware/drivers/).)  
  
 L'operazione dello spooler di stampa per documenti XPS è essenzialmente lo stesso come nelle versioni precedenti di Windows. Tuttavia, è stata migliorata per supportare il percorso di stampa XPS oltre esistente [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] percorso di stampa. Il nuovo percorso di stampa Usa a livello nativo un file di spooling XPS. Mentre i driver di stampante in modalità utente scritti per le versioni precedenti di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] continueranno a funzionare, un driver della stampante XPS (XPSDrv) è necessario per usare il percorso di stampa XPS.  
  
 I vantaggi del percorso di stampa XPS sono significativi e includono:  
  
- Supporto di stampa [!INCLUDE[TLA2#tla_wys](../../../../includes/tla2sharptla-wys-md.md)]  
  
- Supporto nativo di profili colori avanzati che includono 32 bit per canale (bpc), CMYK, colori con nome, molteplici inchiostri e supporto nativo di trasparenza e sfumature.  
  
- Miglioramento delle prestazioni di stampa per entrambi .NET Framework e [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applicazioni basate su.  
  
- Formato XPS standard di settore.  
  
 Per scenari di stampa di base, un'API semplice e intuitiva è disponibile con un singolo punto di ingresso per interfaccia utente, configurazione e processo di invio. Per scenari avanzati, è disponibile un supporto aggiuntivo per la personalizzazione dell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (o nessuna [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), la stampa sincrona o asincrona e le funzionalità di stampa in modalità batch. Entrambe le opzioni forniscono supporto di stampa in modalità di attendibilità completa o parziale.  
  
 XPS è stato progettato con particolare attenzione all'estendibilità. Usando il framework di estendibilità, è possibile aggiungere funzionalità a XPS in modo modulare. Le funzionalità di estensibilità includono:  
  
- Schema di stampa. Lo schema pubblico viene aggiornato regolarmente e consente la rapida estensione delle funzionalità del dispositivo Vedere **PrintTicket e PrintCapabilities** più avanti.  
  
- Pipeline del filtro estensibile. La pipeline filtro di stored procedure estese stampante driver (XPSDrv) è stata progettata per consentire la stampa diretta e scalabile dei documenti XPS. Per altre informazioni, vedere [i driver delle stampanti XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Architettura del percorso di stampa  
 Se entrambe [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e le applicazioni .NET Framework supportano XPS, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e usano le applicazioni Windows Forms un [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] per XPS conversione per poter creare stored procedure estese formattato il contenuto del driver di stampa XPS (XPSDrv). Queste applicazioni non è necessario usare il percorso di stampa XPS e possono continuare a usare [!INCLUDE[TLA#tla_emf](../../../../includes/tlasharptla-emf-md.md)] stampa basata su. Tuttavia, la maggior parte delle funzionalità di stored procedure estese e i miglioramenti disponibili solo per le applicazioni che usano il percorso di stampa XPS.  
  
 Per consentire l'utilizzo di stampanti basate su XPSDrv da [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e le applicazioni Windows Forms, il driver della stampante XPS (XPSDrv) supporta la conversione di [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] per stored procedure estese di formato. Il modello XPSDrv dispone inoltre un convertitore per la stored procedure estese al [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] formato in modo che [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] le applicazioni in grado di stampare [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] documenti. Per [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni, la conversione di stored procedure estese per [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] formato viene eseguito automaticamente tramite il <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> metodi del <xref:System.Windows.Xps.XpsDocumentWriter> classe ogni volta che la coda di stampa di destinazione dell'operazione di scrittura non dispone di un driver XPSDrv. (Applicazioni Windows Form non è possibile stampare [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] documenti.)  
  
 Di seguito viene illustrato il sottosistema di stampa e definisce le parti fornite da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]e quelle definite da fornitori di hardware e software:  
  
 ![Screenshot mostra che sistema di stampa XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Stampa XPS di base  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] definisce sia un'API di base e avanzata. Per le applicazioni che non richiedono la personalizzazione estesa o accedere alla funzionalità XPS completata è disponibile il supporto di stampa di base, imposta. Il supporto di stampa di base viene esposto tramite un controllo finestra di dialogo di stampa che richiede una configurazione minima e offre un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] già familiare all'utente. Molte funzionalità di stored procedure estese sono disponibili tramite questo modello di stampa semplificato.  
  
#### <a name="printdialog"></a>PrintDialog  
 Il <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> controllo fornisce un singolo punto di ingresso per [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configurazione e l'invio di processi di stored procedure estese. Per informazioni su come creare un'istanza del controllo e come usarlo, vedere [Richiamare una finestra di dialogo di stampa](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Stampa XPS avanzata  
 Per accedere all'insieme completo di funzionalità di stored procedure estese, l'API di stampa avanzato deve essere usata. Diverse API pertinenti sono descritte in maggiore dettaglio di seguito. Per un elenco completo di percorso di stampa XPS API, vedere la <xref:System.Windows.Xps> e <xref:System.Printing> riferimenti dello spazio dei nomi.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket e PrintCapabilities  
 Il <xref:System.Printing.PrintTicket> e <xref:System.Printing.PrintCapabilities> classi sono alla base delle funzionalità avanzate di stored procedure estese. Entrambi i tipi di oggetti sono strutture in formato [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] di funzionalità orientate alla stampa quali regole di confronto, stampa fronte-retro, graffatura e così via. Queste strutture sono definite dallo schema di stampa. Un oggetto <xref:System.Printing.PrintTicket> indica a una stampante come elaborare un processo di stampa. La classe <xref:System.Printing.PrintCapabilities> consente di definire le funzionalità di una stampante. Eseguendo una query delle funzionalità di una stampante, è possibile creare un oggetto <xref:System.Printing.PrintTicket> per usare in modo completo tutte le funzionalità supportate di una stampante. Analogamente, è possibile evitare le funzionalità non supportate.  
  
 L'esempio riportato di seguito illustra come eseguire una query della classe <xref:System.Printing.PrintCapabilities> di una stampante e creare un oggetto <xref:System.Printing.PrintTicket> tramite il codice.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer e PrintQueue  
 La classe <xref:System.Printing.PrintServer> rappresenta un server di stampa di rete, mentre la classe <xref:System.Printing.PrintQueue> rappresenta una stampante e la coda del processo di output a essa associata. Insieme, queste API consentono una gestione avanzata del server processi di stampa. La classe <xref:System.Printing.PrintServer>, o una delle relative classi derivate, consente di gestire la classe <xref:System.Printing.PrintQueue>. Il metodo <xref:System.Printing.PrintQueue.AddJob%2A> consente di inserire un nuovo processo di stampa nella coda.  
  
 L'esempio di codice riportato di seguito illustra come creare un oggetto <xref:System.Printing.LocalPrintServer> e come accedere al relativo oggetto <xref:System.Printing.PrintQueue> predefinito tramite il codice.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 Un' <xref:System.Windows.Xps.XpsDocumentWriter>, con i relativi i <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> metodi, viene utilizzato per scrivere documenti XPS in un <xref:System.Printing.PrintQueue>. Ad esempio, il <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> metodo viene utilizzato per restituire un documento XPS e <xref:System.Printing.PrintTicket> in modo sincrono. Il <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> metodo viene utilizzato per restituire un documento XPS e <xref:System.Printing.PrintTicket> in modo asincrono.  
  
 L'esempio riportato di seguito illustra come creare un oggetto <xref:System.Windows.Xps.XpsDocumentWriter> tramite codice.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 I metodi <xref:System.Printing.PrintQueue.AddJob%2A> consentono anche di stampare in diversi modi. Vedere [Stampa di file XPS a livello di codice](how-to-programmatically-print-xps-files.md). per informazioni dettagliate.  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>Percorso di stampa GDI  
 Sebbene [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le applicazioni supportano in modo nativo il percorso di stampa XPS, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e applicazioni Windows Forms possono anche sfruttare i vantaggi di alcune funzionalità di stored procedure estese. Il driver della stampante XPS (XPSDrv) può convertire [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] basato su output in formato XPS. Per scenari avanzati, è supportata la conversione personalizzata del contenuto usando il [Microsoft XPS documento convertitore (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-). In modo analogo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le applicazioni possono anche inviare output al [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] percorso di stampa chiamando uno delle <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> o <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> metodi del <xref:System.Windows.Xps.XpsDocumentWriter> coda di stampa di classi e impostando una stampante non XpsDrv come destinazione.  

Per le applicazioni che non richiedono funzionalità di stored procedure estese o supporto, corrente [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] percorso di stampa rimane invariato.  
  
- Per materiale di riferimento aggiuntivo nel [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] stampare percorso e le varie opzioni di conversione di stored procedure estese, vedere [Microsoft XPS documento convertitore (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) e [i driver delle stampanti XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>Modello di driver XPSDrv  
 Il percorso di stampa XPS migliora l'efficienza dello spooler usando stored procedure estese come il formato nativo dello spool di stampa durante la stampa su una stored procedure estese-driver o una stampante. Il processo di spooling semplificato elimina la necessità di generare un file di spooling intermedio, ad esempio un file di dati [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], prima che il documento venga inviato allo spooler. Tramite più piccoli file di spooling, il percorso di stampa XPS può ridurre il traffico di rete e migliorare le prestazioni di stampa.  
  
 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] è un formato chiuso che rappresenta l'output dell'applicazione come una serie di chiamate a [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] per i servizi di rendering. A differenza di [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], il formato di spooler XPS rappresenta il documento effettivo senza richiedere un'ulteriore interpretazione durante l'output a un driver della stampante basati su XPS (XPSDrv). I driver possono agire direttamente sui dati nel formato. Questa funzionalità elimina le conversioni dei dati e dello spazio colori necessarie quando si usano file [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] e driver della stampante basati su [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)].  
  
 Le dimensioni del file di spooling diminuiscono in genere quando si utilizzano documenti XPS destinati a un driver della stampante XPS (XPSDrv) rispetto a loro [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] equivalenti; esistono tuttavia delle eccezioni:  
  
- Una grafica vettoriale molto complessa, a più livelli o scritta in modo inappropriato può presentare dimensioni maggiori rispetto alla relativa versione bitmap.  
  
- Per scopi di visualizzazione, i file XPS incorporano tipi di carattere del dispositivo, nonché tipi di caratteri basati sul computer. Al contrario, i file di spooling GDI non incorporano alcun tipo di carattere del dispositivo. Tuttavia, entrambi i tipi di carattere presentano sottoinsiemi (vedere di seguito) e i driver della stampante possono rimuovere i tipi di carattere del dispositivo prima di trasmettere il file alla stampante.  
  
 La riduzione delle dimensioni di spooling viene eseguita tramite molteplici meccanismi:  
  
- **Incorporamento di sottoinsiemi di tipi di carattere**. Solo i caratteri utilizzati all'interno del documento effettivo vengono archiviati nel file XPS.  
  
- **Supporto grafico avanzato**. Il supporto nativo di primitive di sfumature e trasparenza evita la rasterizzazione del contenuto nel documento [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
- **Identificazione di risorse comuni**. Le risorse usate più volte (ad esempio un'immagine che rappresenta un logo aziendale) sono considerate risorse condivise e vengono caricate solo una volta.  
  
- **Compressione ZIP**. Tutti i documenti XPS usano la compressione ZIP.  
  
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
- [Convertitore di tipi (MXDC) documenti XPS Microsoft](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
