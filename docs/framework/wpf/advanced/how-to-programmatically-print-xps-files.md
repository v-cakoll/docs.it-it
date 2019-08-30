---
title: 'Procedura: Stampare file XPS a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
ms.openlocfilehash: 6642fad7d20e60a8b92e5860b763511f4fc0be72
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169175"
---
# <a name="how-to-programmatically-print-xps-files"></a>Procedura: Stampare file XPS a livello di codice
È possibile <xref:System.Printing.PrintQueue.AddJob%2A> usare un overload del metodo per stampare [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] i file senza aprire un <xref:System.Windows.Controls.PrintDialog> oggetto o, in generale, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] qualsiasi.  
  
 È inoltre possibile stampare [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file utilizzando i molti <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> metodi <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> e di <xref:System.Windows.Xps.XpsDocumentWriter>. Per altre informazioni, vedere [Stampa di un documento XPS](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90)).  
  
 Un altro modo per [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] eseguire la stampa consiste <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> nell' <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A> usare i metodi <xref:System.Windows.Controls.PrintDialog> o del controllo. Vedere [Richiamare una finestra di dialogo Stampa](how-to-invoke-a-print-dialog.md).  
  
## <a name="example"></a>Esempio  
 I passaggi principali per l'uso del metodo a <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> tre parametri sono i seguenti. L'esempio riportato di seguito offre delle informazioni dettagliate.  
  
1. Determinare se la stampante è una stampante XPSDrv. (Vedere [Panoramica di stampa](printing-overview.md) per altre informazioni su XPSDrv.)  
  
2. Se la stampante non è una stampante XPSDrv, impostare l'apartment del thread a thread singolo.  
  
3. Creare un'istanza di un server di stampa e un oggetto coda di stampa.  
  
4. Chiamare il metodo, specificando il nome di un processo, il file da stampare e <xref:System.Boolean> un flag che indica se la stampante è o meno una stampante XPSDrv.  
  
 Nell'esempio seguente viene illustrato come stampare in blocco tutti i file [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] in una directory. Anche se l'applicazione richiede all'utente di specificare la directory, il metodo a tre <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> parametri non richiede un oggetto [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Può essere usato in qualsiasi percorso di codice in cui si ha un nome file [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] e un percorso che è possibile percorrere.  
  
 L'overload a tre <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> parametri di <xref:System.Printing.PrintQueue.AddJob%2A> deve essere eseguito in un Apartment a thread singolo <xref:System.Boolean> ogni volta `false`che il parametro è, che deve essere quando viene utilizzata una stampante non XPSDrv. Tuttavia, lo stato dell'Apartment predefinito per .NET è più thread. Questa impostazione predefinita deve essere annullata poiché nell'esempio si presuppone una stampante non XPSDrv.  
  
 Ci sono due modi per modificare il valore predefinito. Un modo consiste nel <xref:System.STAThreadAttribute> aggiungere semplicemente (ovvero "`[System.STAThreadAttribute()]`") appena sopra la prima `Main` riga del metodo dell'applicazione (in genere "`static void Main(string[] args)`"). Tuttavia, molte applicazioni richiedono che il `Main` metodo disponga di uno stato di Apartment multithread, quindi è disponibile un secondo metodo: inserire la chiamata a <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> in un thread separato il cui stato Apartment è impostato su <xref:System.Threading.ApartmentState.STA> con <xref:System.Threading.Thread.SetApartmentState%2A>. Nell'esempio seguente si usa la seconda tecnica.  
  
 Di conseguenza, l'esempio inizia con la creazione <xref:System.Threading.Thread> di un'istanza di un oggetto e il passaggio <xref:System.Threading.ThreadStart> di un metodo **PrintXPS** come parametro. (Il metodo **PrintXPS** è definito in un secondo momento nell'esempio.) Poi il thread è impostato su un apartment a thread singolo. Il solo codice rimanente del metodo `Main` avvia il nuovo thread.  
  
 La sostanza dell'esempio è nel metodo `static`**BatchXPSPrinter**. Dopo la creazione di un server di stampa e di una coda, il metodo richiede all'utente una directory contenente i [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] file. Dopo aver convalidato l'esistenza della directory e la \*presenza di file con estensione XPS, il metodo aggiunge ogni file di questo tipo alla coda di stampa. Nell'esempio si presuppone che la stampante non sia XPSDrv, quindi si passa `false` all'ultimo parametro del <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> metodo. Per questo motivo, il metodo convaliderà il [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] markup nel file prima di tentare di convertirlo nel linguaggio di descrizione della pagina della stampante. Se la convalida non riesce, viene generata un'eccezione. Nell'esempio di codice verrà intercettata l'eccezione, se ne informa l'utente e quindi si passa all'elaborazione del file [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] successivo.  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 Se si usa una stampante XPSDrv, allora è possibile impostare il parametro finale su `true`. In questo caso, poiché [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] è il linguaggio di descrizione della pagina della stampante, il metodo invierà il file alla stampante senza convalidarlo né convertirlo in un altro linguaggio di descrizione della pagina. Se si è incerti in fase di progettazione se l'applicazione utilizzerà una stampante XPSDrv, è possibile modificare l'applicazione in modo che legga la <xref:System.Printing.PrintQueue.IsXpsDevice%2A> proprietà e il ramo in base a quanto rilevato.  
  
 Poiché inizialmente saranno disponibili alcune stampanti XPSDrv immediatamente dopo il rilascio di [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] e Microsoft .NET Framework, potrebbe essere necessario mascherare una stampante non XPSDrv come stampante XPSDrv. A tale scopo, aggiungere Pipelineconfig.xml all'elenco dei file nella seguente chiave del Registro di sistema del computer che esegue l'applicazione:  
  
 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\ *\<PseudoXPSPrinter>* \DependentFiles  
  
 dove *\<PseudoXPSPrinter>* è qualsiasi coda di stampa. Il computer deve quindi essere riavviato.  
  
 Questo travestimento consentirà `true` di passare come parametro finale <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> di senza generare un'eccezione, ma poiché  *\<PseudoXPSPrinter >* non è realmente una stampante XPSDrv, verrà stampata solo l'operazione di Garbage Collection.  
  
 **Nota** Per semplicità, l'esempio precedente utilizza la presenza di un' \*estensione XPS come test di un [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]file. Tuttavia, i file [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] non devono necessariamente avere questa estensione. Il [isXPS.exe (strumento di conformità isXPS)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100)) è una delle modalità per testare la [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] validità dei file.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.AddJob%2A>
- <xref:System.Threading.ApartmentState>
- <xref:System.STAThreadAttribute>
- [Documenti XPS](/windows/desktop/printdocs/documents)
- [Stampa di un documento XPS](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90))
- [Threading gestito e non gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [isXPS.exe (strumento di conformità isXPS)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100))
- [Documenti in WPF](documents-in-wpf.md)
- [Panoramica della stampa](printing-overview.md)
