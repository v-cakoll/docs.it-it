---
title: Cenni preliminari sulla stampa
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 35
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f6478f23e6be8875ebe281b83094e4ea1d2e24e4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="printing-overview"></a>Cenni preliminari sulla stampa
Con Microsoft .NET Framework, gli sviluppatori di applicazioni mediante Windows Presentation Foundation (WPF) hanno un ampio set nuovo di stampa e sistema di gestione stampa [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]. Con [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], alcuni dei miglioramenti apportati al sistema di stampa sono anche disponibili agli sviluppatori che creano applicazioni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e a quelli che usano codice non gestito. Questa nuova funzionalità è basata sul nuovo formato di file [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] e sul percorso di stampa [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>Informazioni su XPS  
 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] è un formato di documento elettronico, un formato del file di spooling e un linguaggio di descrizione della pagina. Si tratta di un formato di documento aperto basato sull'uso di [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], [!INCLUDE[TLA#tla_opc](../../../../includes/tlasharptla-opc-md.md)] e di altri standard del settore per creare documenti per più piattaforme. [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] semplifica il processo di creazione, condivisione, stampa, visualizzazione e archiviazione di documenti digitali. Per altre informazioni su [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], visitare il [sito Web XPS](http://www.microsoft.com/xps).  
  
 Varie tecniche di stampa di contenuto basato su [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] tramite [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] vengono illustrate in [Stampa di file XPS a livello di codice](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md). Può essere utile fare riferimento a tali esempi durante la lettura di questo argomento. (Gli sviluppatori di codice non gestito devono vedere la documentazione per il [funzione MXDC_ESCAPE](https://msdn.microsoft.com/library/windows/desktop/dd162739.aspx). Gli sviluppatori di Windows Form devono usare il [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] nella <xref:System.Drawing.Printing> dello spazio dei nomi che non supporta la versione completa [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] percorso di stampa, ma supporta un percorso di stampa GDI XPS ibrido. Vedere **Architettura del percorso di stampa** più avanti.  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>Percorso di stampa XPS  
 Il [!INCLUDE[TLA#tla_metro](../../../../includes/tlasharptla-metro-md.md)] è un nuovo percorso di stampa [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] funzionalità che consente di ridefinire la modalità di gestione stampa nelle applicazioni Windows. Poiché [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] può sostituire un linguaggio di presentazione del documento, ad esempio RTF, un formato di spooler di stampa, ad esempio WMF, e un linguaggio di descrizione della pagina, ad esempio PCL o Postscript, il nuovo percorso di stampa mantiene il formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] dalla pubblicazione dell'applicazione all'elaborazione finale nel dispositivo o nel driver di stampa.  
  
 Il percorso di stampa [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] è basato sul modello del driver della stampante [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] (XPSDrv) e offre agli sviluppatori numerosi vantaggi quali stampa [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] ("what you see is what you get"), supporto del colore migliorato e prestazioni di stampa più elevate. Per altre informazioni su XPSDrv, vedere il [Windows Driver Development Kit](https://msdn.microsoft.com/library/windows/hardware/ff557573.aspx).  
  
 L'operazione dello spooler di stampa per [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] documenti corrisponde essenzialmente come nelle versioni precedenti di Windows. Tuttavia, è ora previsto il supporto del percorso di stampa [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] oltre al percorso di stampa [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] esistente. Il nuovo percorso di stampa usa a livello nativo un file di spooling [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. Anche se i driver della stampante in modalità utente scritti per le versioni precedenti di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] continueranno a funzionare, è necessario disporre di un driver della stampante [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] (XPSDrv) per usare il percorso di stampa [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  
  
 I vantaggi derivanti dall'uso del percorso di stampa [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] sono significativi e includono:  
  
-   Supporto di stampa [!INCLUDE[TLA2#tla_wys](../../../../includes/tla2sharptla-wys-md.md)]  
  
-   Supporto nativo di profili colori avanzati che includono 32 bit per canale (bpc), CMYK, colori con nome, molteplici inchiostri e supporto nativo di trasparenza e sfumature.  
  
-   Miglioramento delle prestazioni di stampa per entrambi .NET Framework e [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applicazioni basate su.  
  
-   Formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] standard del settore.  
  
 Per scenari di stampa di base, è disponibile un'[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] semplice e di uso intuitivo con un solo punto di ingresso per interfaccia utente, configurazione e invio di processi. Per scenari avanzati, è disponibile un supporto aggiuntivo per la personalizzazione dell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (o nessuna [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), la stampa sincrona o asincrona e le funzionalità di stampa in modalità batch. Entrambe le opzioni forniscono supporto di stampa in modalità di attendibilità completa o parziale.  
  
 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] è stato progettato tenendo presente l'estensibilità. Usando il framework di estensibilità, è possibile aggiungere funzionalità a [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] in modo modulare. Le funzionalità di estensibilità includono:  
  
-   Schema di stampa. Lo schema pubblico viene aggiornato regolarmente e consente la rapida estensione delle funzionalità del dispositivo Vedere **PrintTicket e PrintCapabilities** più avanti.  
  
-   Pipeline del filtro estensibile. La pipeline del filtro del driver della stampante [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] (XPSDrv) è progettata per consentire la stampa diretta e scalabile di documenti [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] (Ricerca "XPSDrv" nel [Windows Driver Kit](https://msdn.microsoft.com/library/windows/hardware/ff557573.aspx).)  
  
### <a name="print-path-architecture"></a>Architettura del percorso di stampa  
 Mentre entrambi [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e le applicazioni .NET Framework supportano [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e le applicazioni Windows Form usare un [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] al [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] conversione per poter creare [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] formattato contenuto per il [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]driver della stampante (XPSDrv). Non è necessario che queste applicazioni usino il percorso di stampa [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] e possono continuare a usare la stampa basata su [!INCLUDE[TLA#tla_emf](../../../../includes/tlasharptla-emf-md.md)]. Tuttavia, la maggior parte delle funzionalità e dei miglioramenti offerti da [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] è disponibile unicamente per le applicazioni che usano il percorso di stampa [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  
  
 Per consentire l'utilizzo delle stampanti basate su XPSDrv dal [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e le applicazioni Windows Form, il [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] driver della stampante (XPSDrv) supporta la conversione dei [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] a [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] formato. Il modello XPSDrv dispone inoltre di un convertitore per il formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] - [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)], per consentire alle applicazioni [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] di stampare documenti [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]. Per [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni, la conversione del [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] per [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] formato viene eseguito automaticamente tramite il <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> metodi del <xref:System.Windows.Xps.XpsDocumentWriter> classe ogni volta che la coda di stampa di destinazione dell'operazione di scrittura non dispone un driver XPSDrv. (Applicazioni Windows Form non è possibile stampare [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] documenti.)  
  
 Di seguito viene illustrato il sottosistema di stampa e vengono definite le parti fornite da [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] e quelle definite da fornitori di software e hardware.  
  
 ![Sistema di stampa XPS](../../../../docs/framework/wpf/advanced/media/xpsprint.PNG "XPSPrint")  
  
### <a name="basic-xps-printing"></a>Stampa XPS di base  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è definita un'[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] di base e un'API avanzata. Per le applicazioni che non richiedono una personalizzazione di stampa capillare o l'accesso a tutte le funzionalità [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], è disponibile un supporto di stampa di base. Il supporto di stampa di base viene esposto tramite un controllo finestra di dialogo di stampa che richiede una configurazione minima e offre un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] già familiare all'utente. Molte funzionalità [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] sono disponibili tramite questo modello di stampa semplificato.  
  
#### <a name="printdialog"></a>PrintDialog  
 Il controllo <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> rappresenta un singolo punto di ingresso per l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], la configurazione e l'invio di processi [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. Per informazioni su come creare un'istanza del controllo e come usarlo, vedere [Richiamare una finestra di dialogo di stampa](../../../../docs/framework/wpf/advanced/how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Stampa XPS avanzata  
 Per accedere all'insieme completo delle funzionalità [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], è necessario usare l'[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] di stampa avanzata. Di seguito vengono descritte in dettaglio diverse [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]. Per un elenco completo di [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] percorso di stampa [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], vedere il <xref:System.Windows.Xps> e <xref:System.Printing> riferimenti dello spazio dei nomi.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket e PrintCapabilities  
 Il <xref:System.Printing.PrintTicket> e <xref:System.Printing.PrintCapabilities> classi sono alla base delle funzionalità [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] funzionalità. Entrambi i tipi di oggetti sono strutture in formato [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] di funzionalità orientate alla stampa quali regole di confronto, stampa fronte-retro, graffatura e così via. Queste strutture sono definite dallo schema di stampa. Un oggetto <xref:System.Printing.PrintTicket> indica a una stampante come elaborare un processo di stampa. La classe <xref:System.Printing.PrintCapabilities> consente di definire le funzionalità di una stampante. Eseguendo una query delle funzionalità di una stampante, è possibile creare un oggetto <xref:System.Printing.PrintTicket> per usare in modo completo tutte le funzionalità supportate di una stampante. Analogamente, è possibile evitare le funzionalità non supportate.  
  
 L'esempio riportato di seguito illustra come eseguire una query della classe <xref:System.Printing.PrintCapabilities> di una stampante e creare un oggetto <xref:System.Printing.PrintTicket> tramite il codice.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](../../../../samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer e PrintQueue  
 La classe <xref:System.Printing.PrintServer> rappresenta un server di stampa di rete, mentre la classe <xref:System.Printing.PrintQueue> rappresenta una stampante e la coda del processo di output a essa associata. Insieme, queste [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] consentono una gestione avanzata dei processi di stampa di un server. La classe <xref:System.Printing.PrintServer>, o una delle relative classi derivate, consente di gestire la classe <xref:System.Printing.PrintQueue>. Il metodo <xref:System.Printing.PrintQueue.AddJob%2A> consente di inserire un nuovo processo di stampa nella coda.  
  
 L'esempio di codice riportato di seguito illustra come creare un oggetto <xref:System.Printing.LocalPrintServer> e come accedere al relativo oggetto <xref:System.Printing.PrintQueue> predefinito tramite il codice.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 Un oggetto <xref:System.Windows.Xps.XpsDocumentWriter>, con i relativi metodi <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>, consente di scrivere documenti [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] in un oggetto <xref:System.Printing.PrintQueue>. Ad esempio, il metodo <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> viene usato per emettere un documento[!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]  e un oggetto <xref:System.Printing.PrintTicket> in modo sincrono. Il metodo <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> viene invece usato per emettere un documento [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] e un oggetto <xref:System.Printing.PrintTicket> in modo asincrono.  
  
 L'esempio riportato di seguito illustra come creare un oggetto <xref:System.Windows.Xps.XpsDocumentWriter> tramite codice.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 I metodi <xref:System.Printing.PrintQueue.AddJob%2A> consentono anche di stampare in diversi modi. Vedere [Stampa di file XPS a livello di codice](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md). per informazioni dettagliate.  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>Percorso di stampa GDI  
 Mentre [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le applicazioni in modo nativo supportano il [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] percorso di stampa, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e le applicazioni Windows Forms possono inoltre sfruttare alcune [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] funzionalità. Il driver della stampante [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] (XPSDrv) può convertire l'output basato su [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] nel formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. Per scenari avanzati, è supportata la conversione personalizzata del contenuto utilizzando il [Microsoft XPS documento convertitore (MXDC)](https://msdn.microsoft.com/library/windows/desktop/ff686803.aspx). Analogamente, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni possono inoltre restituire per il [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] percorso di stampa chiamando uno del <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> o <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> metodi del <xref:System.Windows.Xps.XpsDocumentWriter> classe e designare una stampante non XpsDrv come destinazione coda di stampa.  

Per le applicazioni che non richiedono il supporto o la funzionalità [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], il percorso di stampa [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] corrente rimane invariato.  
  
-   Per ulteriore materiale di riferimento sul [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] stampare percorso e le varie [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] opzioni di conversione, vedere [Microsoft XPS documento convertitore (MXDC)](https://msdn.microsoft.com/library/windows/desktop/ff686803.aspx) "XPSDrv" in e il [Windows Driver Kit](https://msdn.microsoft.com/library/windows/hardware/ff557573.aspx).  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>Modello di driver XPSDrv  
 Il percorso di stampa [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] migliora l'efficienza dello spooler usando [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] come formato dello spooler di stampa nativo per la stampa su un driver o una stampante [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. Il processo di spooling semplificato elimina la necessità di generare un file di spooling intermedio, ad esempio un file di dati [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], prima che il documento venga inviato allo spooler. Grazie alle dimensioni ridotte del file di spooling, il percorso di stampa [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] può ridurre il traffico nella rete e migliorare le prestazioni di stampa.  
  
 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] è un formato chiuso che rappresenta l'output dell'applicazione come una serie di chiamate a [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] per i servizi di rendering. A differenza di [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], il formato di spooling [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] rappresenta il documento effettivo senza richiedere un'ulteriore interpretazione al momento dell'output su un driver della stampante [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] (XPSDrv). I driver possono agire direttamente sui dati nel formato. Questa funzionalità elimina le conversioni dei dati e dello spazio colori necessarie quando si usano file [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] e driver della stampante basati su [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)].  
  
 Le dimensioni del file di spooling diminuiscono in genere quando si usano documenti [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] indirizzati a un driver della stampante [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] (XPSDrv), rispetto agli equivalenti [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)]. Esistono tuttavia delle eccezioni:  
  
-   Una grafica vettoriale molto complessa, a più livelli o scritta in modo inappropriato può presentare dimensioni maggiori rispetto alla relativa versione bitmap.  
  
-   Per scopi di visualizzazione, i file XPS incorporano tipi di carattere del dispositivo, nonché tipi di caratteri basati sul computer. Al contrario, i file di spooling GDI non incorporano alcun tipo di carattere del dispositivo. Tuttavia, entrambi i tipi di carattere presentano sottoinsiemi (vedere di seguito) e i driver della stampante possono rimuovere i tipi di carattere del dispositivo prima di trasmettere il file alla stampante.  
  
 La riduzione delle dimensioni di spooling viene eseguita tramite molteplici meccanismi:  
  
-   **Incorporamento di sottoinsiemi di tipi di carattere**. Solo i caratteri usati nel documento effettivo vengono archiviati nel file [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  
  
-   **Supporto grafico avanzato**. Il supporto nativo di primitive di sfumature e trasparenza evita la rasterizzazione del contenuto nel documento [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
-   **Identificazione di risorse comuni**. Le risorse usate più volte (ad esempio un'immagine che rappresenta un logo aziendale) sono considerate risorse condivise e vengono caricate solo una volta.  
  
-   **Compressione ZIP**. Tutti i documenti [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] usano la compressione ZIP.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.PrintDialog>  
 <xref:System.Windows.Xps.XpsDocumentWriter>  
 <xref:System.Windows.Xps.Packaging.XpsDocument>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.PrintQueue>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/printing-how-to-topics.md)  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [XPS](http://www.microsoft.com/xps)  
 [Serializzazione e archiviazione di documenti](../../../../docs/framework/wpf/advanced/document-serialization-and-storage.md)  
 [Documenti XPS Microsoft convertitore (MXDC)](https://msdn.microsoft.com/library/windows/desktop/ff686803.aspx)
