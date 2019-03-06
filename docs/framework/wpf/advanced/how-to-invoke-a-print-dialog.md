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
ms.openlocfilehash: 038e259810111d2d648c72a9f43afabe11a07f29
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358431"
---
# <a name="how-to-invoke-a-print-dialog"></a>Procedura: Richiamare una finestra di dialogo di stampa
Per fornire la possibilità di stampa dall'applicazione, è possibile semplicemente creare e aprire un <xref:System.Windows.Controls.PrintDialog> oggetto.  
  
## <a name="example"></a>Esempio  
 Il controllo <xref:System.Windows.Controls.PrintDialog> rappresenta un singolo punto di ingresso per l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], la configurazione e l'invio di processi [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. Il controllo è facile da usare e può essere creata un'istanza usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] codice o markup. Nell'esempio seguente viene illustrato come creare un'istanza e aprire il controllo nel codice e come stampare da quest'ultimo. Viene inoltre illustrato come assicurarsi che la finestra di dialogo fornirà all'utente la possibilità di impostare un intervallo specifico di pagine. Il codice di esempio si presuppone che esista un file nella radice dell'unità c: di FixedDocumentSequence. Xps.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Dopo aver aperto la finestra di dialogo, gli utenti saranno in grado di selezionare le stampanti installate nel proprio computer. Hanno inoltre la possibilità di selezionare il [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) per creare un [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file anziché la stampa.  
  
> [!NOTE]
>  Il <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> controllo delle [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], come descritto in questo argomento, non deve essere confuso con il <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente di Windows Form.  
  
 In teoria, è possibile usare il <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> metodo senza mai aprire la finestra di dialogo. In tal senso, il controllo può essere utilizzato come un componente di stampa non visti. Ma per motivi di prestazioni sarebbe preferibile utilizzare il il <xref:System.Printing.PrintQueue.AddJob%2A> metodo o uno dei numerosi <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> metodi del <xref:System.Windows.Xps.XpsDocumentWriter>. Per altre informazioni, vedere [a livello di codice stampa di file XPS](how-to-programmatically-print-xps-files.md) e.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.PrintDialog>
- [Documenti in WPF](documents-in-wpf.md)
- [Panoramica della stampa](printing-overview.md)
- [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319)
