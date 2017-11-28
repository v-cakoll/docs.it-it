---
title: 'Procedura: associare un comando a un controllo senza supporto del comando'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f38a6f900ee2b253708da4b63bdc2f474fa3ab1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>Procedura: associare un comando a un controllo senza supporto del comando
Nell'esempio seguente viene illustrato come associare un <xref:System.Windows.Input.RoutedCommand> per un <xref:System.Windows.Controls.Control> che non dispongono del supporto incorporato per il comando.  Per un esempio completo in cui i comandi sono associati a più origini, vedere l'esempio [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980) (Creare un esempio di oggetto RoutedCommand personalizzato).  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce una libreria di comandi comuni usati regolarmente dai programmatori di applicazioni.  Le classi che costituiscono la libreria del comando sono: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, e <xref:System.Windows.Documents.EditingCommands>.  
  
 Il metodo statico <xref:System.Windows.Input.RoutedCommand> gli oggetti che compongono queste classi forniscono la logica di comando.  La logica per il comando è associata al comando con un <xref:System.Windows.Input.CommandBinding>.  Tuttavia, molti controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispone del supporto incorporato per alcuni dei comandi nella libreria del comando.  <xref:System.Windows.Controls.TextBox>, ad esempio, supporta molti dei comandi di modifica dell'applicazione, ad esempio <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, e <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Lo sviluppatore dell'applicazione non deve eseguire operazioni particolari per garantire il funzionamento di questi comandi con tali controlli.  Se il <xref:System.Windows.Controls.TextBox> è la destinazione di comando quando viene eseguito il comando, gestirà il comando utilizzando il <xref:System.Windows.Input.CommandBinding> che è incorporato nel controllo.  
  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Controls.Button> come l'origine del comando per il <xref:System.Windows.Input.ApplicationCommands.Open%2A> comando.  Oggetto <xref:System.Windows.Input.CommandBinding> creato che associa l'oggetto specificato <xref:System.Windows.Input.CanExecuteRoutedEventHandler> e <xref:System.Windows.Input.CanExecuteRoutedEventHandler> con il <xref:System.Windows.Input.RoutedCommand>.  
  
 Innanzitutto, viene creato l'origine del comando.  Oggetto <xref:System.Windows.Controls.Button> viene utilizzato come origine del comando.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Successivamente, il <xref:System.Windows.Input.ExecutedRoutedEventHandler> e <xref:System.Windows.Input.CanExecuteRoutedEventHandler> vengono creati.  Il <xref:System.Windows.Input.ExecutedRoutedEventHandler> apre semplicemente un <xref:System.Windows.MessageBox> per indicare che il comando eseguito.  Il <xref:System.Windows.Input.CanExecuteRoutedEventHandler> imposta il <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> proprietà `true`.  In genere, può eseguire gestore eseguirebbe controlli più affidabile per vedere se è Impossibile eseguire il comando sulla destinazione del comando corrente.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Infine, un <xref:System.Windows.Input.CommandBinding> viene creato nella directory principale <xref:System.Windows.Window> dell'applicazione che associa i gestori di eventi indirizzati per il <xref:System.Windows.Input.ApplicationCommands.Open%2A> comando.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Associare un comando a un controllo con supporto dei comandi](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
