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
ms.openlocfilehash: 6d7bc322079718d17a921ef34af79145b021e3a7
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636094"
---
# <a name="how-to-invoke-a-print-dialog"></a>Procedura: richiamare una finestra di dialogo di stampa
Per consentire la stampa dall'applicazione, è possibile creare e aprire semplicemente un oggetto <xref:System.Windows.Controls.PrintDialog>.  
  
## <a name="example"></a>Esempio  
 Il controllo <xref:System.Windows.Controls.PrintDialog> fornisce un singolo punto di ingresso per [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configurazione e invio di processi XPS. Il controllo è facile da usare ed è possibile crearne un'istanza usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup o codice. Nell'esempio seguente viene illustrato come creare un'istanza di e come aprire il controllo nel codice e come stamparlo. Viene inoltre illustrato come assicurarsi che la finestra di dialogo fornisca all'utente la possibilità di impostare un intervallo specifico di pagine. Nel codice di esempio si presuppone che esista un file FixedDocumentSequence. XPS nella radice dell'unità C:.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Una volta aperta la finestra di dialogo, gli utenti saranno in grado di effettuare una selezione tra le stampanti installate nel computer. Hanno inoltre la possibilità di selezionare il writer di [documenti XPS Microsoft](https://go.microsoft.com/fwlink/?LinkId=147319) per creare un file XPS (XML Paper Specification) anziché stampare.  
  
> [!NOTE]
> Il controllo <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> di WPF, descritto in questo argomento, non dovrebbe essere confuso con il componente <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> di Windows Forms.  
  
 In modo esplicito, è possibile usare il metodo <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> senza mai aprire la finestra di dialogo. In questo senso, il controllo può essere usato come componente di stampa non visibile. Per motivi di prestazioni, tuttavia, sarebbe preferibile usare il metodo <xref:System.Printing.PrintQueue.AddJob%2A> o uno dei molti metodi <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> della <xref:System.Windows.Xps.XpsDocumentWriter>. Per ulteriori informazioni, vedere la pagina relativa alla [stampa di file XPS](how-to-programmatically-print-xps-files.md) e a livello di codice.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.PrintDialog>
- [Documenti in WPF](documents-in-wpf.md)
- [Panoramica della stampa](printing-overview.md)
- [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319)
