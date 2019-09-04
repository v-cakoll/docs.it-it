---
title: 'Procedura: Richiamare una finestra di dialogo di stampa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 4bad8158925fea8af529f70f92aad74e2a6bbec0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254105"
---
# <a name="how-to-invoke-a-print-dialog"></a>Procedura: Richiamare una finestra di dialogo di stampa
Per consentire la stampa dall'applicazione, è possibile creare e aprire semplicemente un <xref:System.Windows.Controls.PrintDialog> oggetto.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.PrintDialog> controllo fornisce un singolo punto di ingresso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]per l'invio di processi, configurazione e XPS. Il controllo è facile da usare ed è possibile crearne un'istanza [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] usando il markup o il codice. Nell'esempio seguente viene illustrato come creare un'istanza di e come aprire il controllo nel codice e come stamparlo. Viene inoltre illustrato come assicurarsi che la finestra di dialogo fornisca all'utente la possibilità di impostare un intervallo specifico di pagine. Nel codice di esempio si presuppone che esista un file FixedDocumentSequence. XPS nella radice dell'unità C:.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Una volta aperta la finestra di dialogo, gli utenti saranno in grado di effettuare una selezione tra le stampanti installate nel computer. Hanno inoltre la possibilità di selezionare il writer di [documenti XPS Microsoft](https://go.microsoft.com/fwlink/?LinkId=147319) per creare un file XPS (XML Paper Specification) anziché stampare.  
  
> [!NOTE]
> Il <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> controllo di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], descritto in questo argomento, non deve essere confuso con il <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente di Windows Forms.  
  
 In modo esplicito, è possibile <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> usare il metodo senza mai aprire la finestra di dialogo. In questo senso, il controllo può essere usato come componente di stampa non visibile. Tuttavia, per motivi di prestazioni, è preferibile usare il <xref:System.Printing.PrintQueue.AddJob%2A> metodo o uno dei molti <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> metodi e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> di <xref:System.Windows.Xps.XpsDocumentWriter>. Per ulteriori informazioni, vedere la pagina relativa alla [stampa di file XPS](how-to-programmatically-print-xps-files.md) e a livello di codice.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.PrintDialog>
- [Documenti in WPF](documents-in-wpf.md)
- [Panoramica della stampa](printing-overview.md)
- [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319)
