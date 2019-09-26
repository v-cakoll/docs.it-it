---
title: 'Procedura: Associare un comando a un controllo senza supporto dei comandi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
ms.openlocfilehash: 3ae45c9a9e33a3cb53ada6e1e5430ae0f9e6c198
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "71263298"
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>Procedura: Associare un comando a un controllo senza supporto dei comandi
Nell'esempio seguente viene illustrato come associare una classe <xref:System.Windows.Input.RoutedCommand> a una classe <xref:System.Windows.Controls.Control> che non dispone del supporto incorporato per il comando.  Per un esempio completo in cui i comandi sono associati a più origini, vedere l'esempio [Create a Custom RoutedCommand Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand) (Creare un esempio di oggetto RoutedCommand personalizzato).  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce una libreria di comandi comuni usati regolarmente dai programmatori di applicazioni.  Le classi che costituiscono la libreria del comando sono: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> e <xref:System.Windows.Documents.EditingCommands>.  
  
 Gli oggetti <xref:System.Windows.Input.RoutedCommand> statici che costituiscono queste classi non forniscono la logica per il comando.  La logica per il comando è associata al comando con un <xref:System.Windows.Input.CommandBinding>.  Molti controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispongono del supporto incorporato per alcuni comandi della libreria di comandi.  <xref:System.Windows.Controls.TextBox>, ad esempio, supporta molti dei comandi di modifica dell'applicazione, ad esempio <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> e <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Lo sviluppatore dell'applicazione non deve eseguire operazioni particolari per garantire il funzionamento di questi comandi con tali controlli.  Se la destinazione del comando eseguito è <xref:System.Windows.Controls.TextBox>, il comando verrà gestito utilizzando il <xref:System.Windows.Input.CommandBinding> incorporato nel controllo.  
  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Controls.Button> come origine del comando <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  Viene creata una classe <xref:System.Windows.Input.CommandBinding> che associa il metodo <xref:System.Windows.Input.CanExecuteRoutedEventHandler> specificato e il metodo <xref:System.Windows.Input.CanExecuteRoutedEventHandler> con la classe <xref:System.Windows.Input.RoutedCommand>.  
  
 Innanzitutto, viene creata l'origine del comando.  Una classe <xref:System.Windows.Controls.Button> viene utilizzata come origine del comando.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Successivamente, vengono creati i metodi <xref:System.Windows.Input.ExecutedRoutedEventHandler> e <xref:System.Windows.Input.CanExecuteRoutedEventHandler>.  Il metodo <xref:System.Windows.Input.ExecutedRoutedEventHandler> apre semplicemente una classe <xref:System.Windows.MessageBox> per indicare che il comando è stato eseguito.  Il metodo <xref:System.Windows.Input.CanExecuteRoutedEventHandler> imposta la proprietà <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> su `true`.  In genere, il gestore CanExecute eseguirebbe controlli più approfonditi per vedere se è possibile eseguire il comando sulla destinazione del comando corrente.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Infine, viene creata una classe <xref:System.Windows.Input.CommandBinding> nella classe <xref:System.Windows.Window> principale dell'applicazione che associa i gestori di eventi indirizzati al comando <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sull'esecuzione di comandi](commanding-overview.md)
- [Associare un comando a un controllo con supporto dei comandi](how-to-hook-up-a-command-to-a-control-with-command-support.md)
