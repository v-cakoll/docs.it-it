---
title: 'Procedura: stampa di file XPS a livello di codice'
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
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b58e617fb04ecaba45ed655dc650459e89453dd
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2018
---
# <a name="how-to-programmatically-print-xps-files"></a>Procedura: stampa di file XPS a livello di codice
È possibile utilizzare uno degli overload del <xref:System.Printing.PrintQueue.AddJob%2A> metodo per la stampa [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file senza aprire un <xref:System.Windows.Controls.PrintDialog> o, in generale, qualsiasi [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] affatto.  
  
 È inoltre possibile stampare [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file utilizzando i diversi <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> metodi di <xref:System.Windows.Xps.XpsDocumentWriter>. Per altre informazioni, vedere [Stampa di un documento XPS](http://msdn.microsoft.com/library/849555c8-0c4e-48c0-86bc-a5494c69b36c).  
  
 Un altro metodo di stampa [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] consiste nell'utilizzare il <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> o <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A> metodi il <xref:System.Windows.Controls.PrintDialog> controllo. Vedere [Richiamare una finestra di dialogo Stampa](../../../../docs/framework/wpf/advanced/how-to-invoke-a-print-dialog.md).  
  
## <a name="example"></a>Esempio  
 I passaggi principali per l'utilizzo del parametro di tre <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> metodo sono i seguenti. L'esempio riportato di seguito offre delle informazioni dettagliate.  
  
1.  Determinare se la stampante è una stampante XPSDrv. (Vedere [Panoramica di stampa](../../../../docs/framework/wpf/advanced/printing-overview.md) per altre informazioni su XPSDrv.)  
  
2.  Se la stampante non è una stampante XPSDrv, impostare l'apartment del thread a thread singolo.  
  
3.  Creare un'istanza di un server di stampa e un oggetto coda di stampa.  
  
4.  Chiamare il metodo, specificando un nome di processo, il file da stampare e un <xref:System.Boolean> flag che indica se la stampante è una stampante XPSDrv o meno.  
  
 Nell'esempio seguente viene illustrato come stampare in blocco tutti i file [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] in una directory. Anche se l'applicazione richiede all'utente di specificare la directory, i tre parametri <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> metodo non richiede un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Può essere usato in qualsiasi percorso di codice in cui si ha un nome file [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] e un percorso che è possibile percorrere.  
  
 I tre parametri <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> overload di <xref:System.Printing.PrintQueue.AddJob%2A> deve essere eseguito in un apartment a thread singolo ogni volta che il <xref:System.Boolean> parametro `false`, che deve essere quando viene utilizzata una stampante non XPSDrv. Tuttavia, lo stato dell'apartment predefinito per [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] è a più thread. Questa impostazione predefinita deve essere annullata poiché nell'esempio si presuppone una stampante non XPSDrv.  
  
 Ci sono due modi per modificare il valore predefinito. Un modo consiste nell'aggiungere semplicemente il <xref:System.STAThreadAttribute> (vale a dire, "`[System.STAThreadAttribute()]`") appena sopra la riga prima dell'applicazione `Main` metodo (in genere "`static void Main(string[] args)`"). Tuttavia, molte applicazioni che richiedono il `Main` metodo hanno uno stato di apartment a thread multipli, pertanto non c'è un secondo metodo: inserire la chiamata a <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> in un thread separato, il cui stato di apartment è impostata su <xref:System.Threading.ApartmentState.STA> con <xref:System.Threading.Thread.SetApartmentState%2A>. Nell'esempio seguente si usa la seconda tecnica.  
  
 Di conseguenza, l'esempio inizia creando un <xref:System.Threading.Thread> oggetto e passando un **PrintXPS** metodo come la <xref:System.Threading.ThreadStart> parametro. (Il metodo **PrintXPS** è definito in un secondo momento nell'esempio.) Poi il thread è impostato su un apartment a thread singolo. Il solo codice rimanente del metodo `Main` avvia il nuovo thread.  
  
 La sostanza dell'esempio è nel metodo `static`**BatchXPSPrinter**. Dopo la creazione di un server di stampa e di una coda, il metodo richiede all'utente una directory contenente i [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] file. Dopo aver validato l'esistenza della directory e la presenza di file con estensione xps, il metodo aggiunge ciascuno di questi file alla coda di stampa. Nell'esempio si presuppone che la stampante non XPSDrv, viene passato `false` all'ultimo parametro di <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> metodo. Per questo motivo, il metodo convaliderà il [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] markup nel file prima di tentare di convertirlo nel linguaggio di descrizione della pagina della stampante. Se la convalida non riesce, viene generata un'eccezione. Nell'esempio di codice verrà intercettata l'eccezione, se ne informa l'utente e quindi si passa all'elaborazione del file [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] successivo.  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 Se si usa una stampante XPSDrv, allora è possibile impostare il parametro finale su `true`. In questo caso, poiché [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] è il linguaggio di descrizione della pagina della stampante, il metodo invierà il file alla stampante senza convalidarlo né convertirlo in un altro linguaggio di descrizione della pagina. Se non si è certi in fase di progettazione indica se l'applicazione utilizzerà una stampante XPSDrv, è possibile modificare l'applicazione affinché venga letta la <xref:System.Printing.PrintQueue.IsXpsDevice%2A> proprietà e la diramazione in base a quanto rilevato.  
  
 Poiché saranno poche all'inizio le stampanti XPSDrv disponibili immediatamente dopo il rilascio di [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] e [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], potrebbe essere necessario far passare una stampante non XPSDrv per una stampante XPSDrv. A tale scopo, aggiungere Pipelineconfig.xml all'elenco dei file nella seguente chiave del Registro di sistema del computer che esegue l'applicazione:  
  
 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\*\<PseudoXPSPrinter>*\DependentFiles  
  
 dove *\<PseudoXPSPrinter>* è qualsiasi coda di stampa. Il computer deve quindi essere riavviato.  
  
 In questo modo è possibile passare `true` come parametro finale di <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> senza causare un'eccezione, tuttavia, poiché  *\<PseudoXPSPrinter >* non sono in effetti una stampante XPSDrv, verrà stampato.  
  
 **Nota** Per semplicità, nell'esempio viene usata la presenza di un'estensione xps come prova che un file è [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]. Tuttavia, i file [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] non devono necessariamente avere questa estensione. Il [isXPS.exe (strumento di conformità isXPS)](http://msdn.microsoft.com/library/bfbb433f-7ab6-417a-90f0-71443d76bcb3) è una delle modalità per testare la [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] validità dei file.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.AddJob%2A>  
 <xref:System.Threading.ApartmentState>  
 <xref:System.STAThreadAttribute>  
 [XPS](http://www.microsoft.com/xps)  
 [Stampa un documento XPS](http://msdn.microsoft.com/library/849555c8-0c4e-48c0-86bc-a5494c69b36c)  
 [Threading gestito e non gestito](http://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5)  
 [isXPS.exe (strumento di conformità isXPS)](http://msdn.microsoft.com/library/bfbb433f-7ab6-417a-90f0-71443d76bcb3)  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)
