---
title: 'Procedura: Creare un oggetto RoutedCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: 73a5337cae61a38e10f3ddd7dbe654d7fae616b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735740"
---
# <a name="how-to-create-a-routedcommand"></a>Procedura: Creare un oggetto RoutedCommand
Questo esempio viene illustrato come creare una classe personalizzata <xref:System.Windows.Input.RoutedCommand> e come implementare il comando personalizzato tramite la creazione di un <xref:System.Windows.Input.ExecutedRoutedEventHandler> e una <xref:System.Windows.Input.CanExecuteRoutedEventHandler> e il ricollegamento di un <xref:System.Windows.Input.CommandBinding>.  Per altre informazioni sull'esecuzione di comandi, vedere la [Cenni preliminari](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## <a name="example"></a>Esempio  
 Il primo passaggio nella creazione di un <xref:System.Windows.Input.RoutedCommand> è la definizione di comando e crearne un'istanza.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 Per usare il comando in un'applicazione, è necessario creare i gestori di eventi che definiscono il comando non  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 Successivamente, un <xref:System.Windows.Input.CommandBinding> viene creato il comando che associa i gestori di eventi. Il <xref:System.Windows.Input.CommandBinding> viene creato in un oggetto specifico.  Questo oggetto definisce l'ambito del <xref:System.Windows.Input.CommandBinding> nell'albero degli elementi  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 Il passaggio finale consiste nel richiamare il comando.  Un modo per richiamare un comando consiste nell'associare a un <xref:System.Windows.Input.ICommandSource>, ad esempio un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 Quando si fa clic sul pulsante, il <xref:System.Windows.Input.RoutedCommand.Execute%2A> metodo sull'oggetto personalizzato <xref:System.Windows.Input.RoutedCommand> viene chiamato.  Il <xref:System.Windows.Input.RoutedCommand> genera il <xref:System.Windows.Input.CommandManager.PreviewExecuted> e <xref:System.Windows.Input.CommandManager.Executed> eventi indirizzati.  Questi eventi attraversano l'albero degli elementi cercando un <xref:System.Windows.Input.CommandBinding> per questo particolare comando.  Se un <xref:System.Windows.Input.CommandBinding> viene trovato, il <xref:System.Windows.Input.ExecutedRoutedEventHandler> associati <xref:System.Windows.Input.CommandBinding> viene chiamato.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Input.RoutedCommand>
- [Panoramica sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md)
