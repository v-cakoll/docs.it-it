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
ms.openlocfilehash: 75a4160366766efbd19d6e8ae26fbec102e7f95b
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924500"
---
# <a name="how-to-invoke-a-print-dialog"></a>Procedura: richiamare una finestra di dialogo di stampa
Per consentire la stampa dall'applicazione, è possibile creare e aprire semplicemente un <xref:System.Windows.Controls.PrintDialog> oggetto.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.PrintDialog> controllo fornisce un singolo punto di ingresso per l' [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] invio di processi, configurazione e XPS. Il controllo è facile da usare ed è possibile crearne un'istanza usando il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup o il codice. Nell'esempio seguente viene illustrato come creare un'istanza di e come aprire il controllo nel codice e come stamparlo. Viene inoltre illustrato come assicurarsi che la finestra di dialogo fornisca all'utente la possibilità di impostare un intervallo specifico di pagine. Nel codice di esempio si presuppone che esista un file FixedDocumentSequence. XPS nella radice dell'unità C:.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Una volta aperta la finestra di dialogo, gli utenti saranno in grado di effettuare una selezione tra le stampanti installate nel computer. Hanno inoltre la possibilità di selezionare il writer di [documenti XPS Microsoft](/windows/win32/printdocs/microsoft-xps-document-writer) per creare un file XPS (XML Paper Specification) anziché stampare.  
  
> [!NOTE]
> Il <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> controllo di WPF, descritto in questo argomento, non dovrebbe essere confuso con il <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente di Windows Forms.  
  
 In modo esplicito, è possibile usare il <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> metodo senza mai aprire la finestra di dialogo. In questo senso, il controllo può essere usato come componente di stampa non visibile. Tuttavia, per motivi di prestazioni, è preferibile usare il <xref:System.Printing.PrintQueue.AddJob%2A> metodo o uno dei molti <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> metodi e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> di <xref:System.Windows.Xps.XpsDocumentWriter> . Per ulteriori informazioni, vedere la pagina relativa alla [stampa di file XPS a livello di codice](how-to-programmatically-print-xps-files.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.PrintDialog>
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sulla stampa](printing-overview.md)
- [Microsoft XPS Document Writer](/windows/win32/printdocs/microsoft-xps-document-writer)
