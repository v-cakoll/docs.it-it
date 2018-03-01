---
title: 'Procedura: creare un oggetto RoutedCommand'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 449b55d07aa0119ff23c8642ca83b0989f5b1d4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-routedcommand"></a>Procedura: creare un oggetto RoutedCommand
In questo esempio viene illustrato come creare un oggetto personalizzato <xref:System.Windows.Input.RoutedCommand> e come implementare il comando personalizzato creando una <xref:System.Windows.Input.ExecutedRoutedEventHandler> e <xref:System.Windows.Input.CanExecuteRoutedEventHandler> e associarle a un <xref:System.Windows.Input.CommandBinding>.  Per ulteriori informazioni sui comandi, vedere il [panoramica dei comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## <a name="example"></a>Esempio  
 Il primo passaggio nella creazione di un <xref:System.Windows.Input.RoutedCommand> è la definizione di comando e istanza.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 Per utilizzare il comando in un'applicazione, è necessario creare i gestori di eventi che consentono di definire il comando non  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 Successivamente, un <xref:System.Windows.Input.CommandBinding> viene creato il comando che associa i gestori di eventi. Il <xref:System.Windows.Input.CommandBinding> viene creato in un oggetto specifico.  Questo oggetto definisce l'ambito del <xref:System.Windows.Input.CommandBinding> nell'albero degli elementi  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 Il passaggio finale consiste nel richiamare il comando.  Per richiamare un comando è possibile associarlo a un <xref:System.Windows.Input.ICommandSource>, ad esempio un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 Quando si fa clic sul pulsante, il <xref:System.Windows.Input.RoutedCommand.Execute%2A> metodo personalizzato <xref:System.Windows.Input.RoutedCommand> viene chiamato.  Il <xref:System.Windows.Input.RoutedCommand> genera il <xref:System.Windows.Input.CommandManager.PreviewExecuted> e <xref:System.Windows.Input.CommandManager.Executed> gli eventi indirizzati.  Questi eventi attraversano l'albero degli elementi cercando un <xref:System.Windows.Input.CommandBinding> per questo comando particolare.  Se un <xref:System.Windows.Input.CommandBinding> viene trovato, il <xref:System.Windows.Input.ExecutedRoutedEventHandler> associato <xref:System.Windows.Input.CommandBinding> viene chiamato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Input.RoutedCommand>  
 [Panoramica sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md)
