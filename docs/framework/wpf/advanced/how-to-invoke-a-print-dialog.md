---
title: 'Procedura: richiamare una finestra di dialogo di stampa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: f94a965f724e85fb63ed9c98ebddba40938eb9b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545558"
---
# <a name="how-to-invoke-a-print-dialog"></a>Procedura: richiamare una finestra di dialogo di stampa
Per fornire la possibilità di stampa dall'applicazione, è possibile semplicemente creare e aprire un <xref:System.Windows.Controls.PrintDialog> oggetto.  
  
## <a name="example"></a>Esempio  
 Il controllo <xref:System.Windows.Controls.PrintDialog> rappresenta un singolo punto di ingresso per l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], la configurazione e l'invio di processi [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. Il controllo è facile da usare e può essere creata un'istanza tramite [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup o codice. Nell'esempio seguente viene illustrato come creare un'istanza e aprire il controllo nel codice e come stampare da esso. Viene inoltre illustrato come assicurarsi che la finestra di dialogo consenta all'utente la possibilità di impostare un intervallo specifico di pagine. Nell'esempio di codice si presuppone che sia presente un file FixedDocumentSequence. XPS nella radice dell'unità c.  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Dopo avere aperto la finestra di dialogo, è possibile che gli utenti saranno in grado di selezionare le stampanti installate nel computer. Hanno inoltre la possibilità di selezionare il [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) per creare un [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file anziché la stampa.  
  
> [!NOTE]
>  Il <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> controllo di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], cui è descritto in questo argomento, non deve essere confuso con il <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente di Windows Form.  
  
 In teoria, è possibile utilizzare il <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> metodo senza mai aprire la finestra di dialogo. In tal senso, il controllo può essere utilizzato come un componente di stampa non visibili. Ma per motivi di prestazioni, sarebbe preferibile utilizzare il di <xref:System.Printing.PrintQueue.AddJob%2A> metodo o una delle numerose <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> metodi il <xref:System.Windows.Xps.XpsDocumentWriter>. Per ulteriori informazioni, vedere [a livello di programmazione i file di stampa XPS](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) e.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.PrintDialog>  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)
