---
title: 'Procedura: attivare un comando'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
ms.openlocfilehash: 81ae2e46c4fdd8b46e2b72b9a1430437ebfe97b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545282"
---
# <a name="how-to-enable-a-command"></a>Procedura: attivare un comando
Nell'esempio riportato di seguito viene illustrato l'utilizzo dei comandi [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Nell'esempio viene illustrato come associare un <xref:System.Windows.Input.RoutedCommand> per un <xref:System.Windows.Controls.Button>, creare un <xref:System.Windows.Input.CommandBinding>e creare i gestori di eventi che implementano il <xref:System.Windows.Input.RoutedCommand>.  Per ulteriori informazioni sui comandi, vedere il [panoramica dei comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## <a name="example"></a>Esempio  
 La prima sezione di codice crea il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], costituito da un <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.StackPanel>e crea un <xref:System.Windows.Input.CommandBinding> che associa i gestori di comando con il <xref:System.Windows.Input.RoutedCommand>.  
  
 Il <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà del <xref:System.Windows.Controls.Button> è associato il <xref:System.Windows.Input.ApplicationCommands.Close%2A> comando.  
  
 Il <xref:System.Windows.Input.CommandBinding> viene aggiunto per il <xref:System.Windows.Input.CommandBindingCollection> della radice <xref:System.Windows.Window>. Il <xref:System.Windows.Input.CommandBinding.Executed> e <xref:System.Windows.Input.CommandBinding.CanExecute> i gestori eventi vengono associati a questa associazione e associati il <xref:System.Windows.Input.ApplicationCommands.Close%2A> comando.  
  
 Senza il <xref:System.Windows.Input.CommandBinding> non vi è alcuna logica di comando, ma solo un meccanismo per richiamare il comando.  Quando il <xref:System.Windows.Controls.Button> si fa clic, il <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> viene generato il comando sulla destinazione seguita dal <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.  Questi eventi attraversano l'albero degli elementi cercando un <xref:System.Windows.Input.CommandBinding> per quel comando specifico.  Vale la pena notare che poiché <xref:System.Windows.RoutedEvent> tunnel e a bolle tramite la struttura ad albero, prestare attenzione nella posizione in cui il <xref:System.Windows.Input.CommandBinding> viene inserito.   Se il <xref:System.Windows.Input.CommandBinding> si trova in un elemento di pari livello di destinazione del comando o un altro nodo che non appartiene alla route del <xref:System.Windows.RoutedEvent>, <xref:System.Windows.Input.CommandBinding> non sarà accessibile.  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 La sezione successiva di codice implementa il <xref:System.Windows.Input.CommandManager.Executed> e <xref:System.Windows.Input.CommandBinding.CanExecute> gestori eventi.  
  
 Il <xref:System.Windows.Input.CommandManager.Executed> gestore chiama un metodo per chiudere il file aperto.  Il <xref:System.Windows.Input.CommandBinding.CanExecute> gestore chiama un metodo per determinare se un file è aperto.  Se un file è aperto, <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> è impostato su `true`; in caso contrario, viene impostato su `false`.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md)
