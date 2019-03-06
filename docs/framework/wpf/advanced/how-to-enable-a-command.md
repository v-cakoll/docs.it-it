---
title: 'Procedura: Attivare un comando'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
ms.openlocfilehash: a24a7a31154de58051677ba41496fcf4da3f2568
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355064"
---
# <a name="how-to-enable-a-command"></a>Procedura: Attivare un comando
Nell'esempio seguente illustra l'utilizzo dei comandi in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Nell'esempio viene illustrato come associare un <xref:System.Windows.Input.RoutedCommand> a un <xref:System.Windows.Controls.Button>, creare un <xref:System.Windows.Input.CommandBinding>e creare i gestori di eventi che implementano il <xref:System.Windows.Input.RoutedCommand>.  Per altre informazioni sull'esecuzione di comandi, vedere la [Cenni preliminari](commanding-overview.md).  
  
## <a name="example"></a>Esempio  
 La prima sezione di codice crea il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], che è costituito un <xref:System.Windows.Controls.Button> e una <xref:System.Windows.Controls.StackPanel>e crea un <xref:System.Windows.Input.CommandBinding> che associa i gestori di comando con il <xref:System.Windows.Input.RoutedCommand>.  
  
 Il <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà del <xref:System.Windows.Controls.Button> è associato il <xref:System.Windows.Input.ApplicationCommands.Close%2A> comando.  
  
 Il <xref:System.Windows.Input.CommandBinding> viene aggiunto per il <xref:System.Windows.Input.CommandBindingCollection> della radice <xref:System.Windows.Window>. Il <xref:System.Windows.Input.CommandBinding.Executed> e <xref:System.Windows.Input.CommandBinding.CanExecute> gestori eventi sono associati a questa associazione e associati i <xref:System.Windows.Input.ApplicationCommands.Close%2A> comando.  
  
 Senza il <xref:System.Windows.Input.CommandBinding> non vi è alcuna logica di comando, ma solo un meccanismo per richiamare il comando.  Quando il <xref:System.Windows.Controls.Button> viene selezionata, il <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> viene generato il comando sulla destinazione seguita dal <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.  Questi eventi attraversano l'albero degli elementi cercando un <xref:System.Windows.Input.CommandBinding> per quel comando specifico.  Vale la pena notare che, poiché <xref:System.Windows.RoutedEvent> tunneling e bubbling attraverso l'albero degli elementi, prestare attenzione nella posizione in cui il <xref:System.Windows.Input.CommandBinding> viene inserito.   Se il <xref:System.Windows.Input.CommandBinding> si trova in un elemento di pari livello di destinazione del comando o un altro nodo che non è presente nella route del <xref:System.Windows.RoutedEvent>, il <xref:System.Windows.Input.CommandBinding> non sarà accessibile.  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 La sezione successiva del codice implementa il <xref:System.Windows.Input.CommandManager.Executed> e <xref:System.Windows.Input.CommandBinding.CanExecute> gestori eventi.  
  
 Il <xref:System.Windows.Input.CommandManager.Executed> gestore chiama un metodo per chiudere il file aperto.  Il <xref:System.Windows.Input.CommandBinding.CanExecute> gestore chiama un metodo per determinare se un file è aperto.  Se un file è aperto <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> è impostata su `true`; in caso contrario, impostarlo su `false`.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica sull'esecuzione di comandi](commanding-overview.md)
