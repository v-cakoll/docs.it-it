---
title: 'Procedura: Associare un comando a un controllo con supporto del comando'
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
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61148e1249f7bfcf319c3be4a30c706c5c4dc344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-command-support"></a>Procedura: Associare un comando a un controllo con supporto del comando
Nell'esempio seguente viene illustrato come associare un <xref:System.Windows.Input.RoutedCommand> per un <xref:System.Windows.Controls.Control> che dispone del supporto per il comando incorporato.  Per un esempio completo in cui i comandi sono associati a più origini, vedere l'esempio [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980) (Creare un esempio di oggetto RoutedCommand personalizzato).  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce una libreria di comandi comuni usati regolarmente dai programmatori di applicazioni.  Le classi che costituiscono la libreria del comando sono: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, e <xref:System.Windows.Documents.EditingCommands>.  
  
 Il metodo statico <xref:System.Windows.Input.RoutedCommand> gli oggetti che compongono queste classi forniscono la logica di comando.  La logica per il comando è associata al comando con un <xref:System.Windows.Input.CommandBinding>.  Alcuni controlli dispongono di CommandBinding incorporati per determinati comandi.  Questo meccanismo consente di mantenere invariata la semantica di un comando, mentre l'implementazione effettiva può cambiare.  Oggetto <xref:System.Windows.Controls.TextBox>, ad esempio, gestisce la <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando in modo diverso rispetto a un controllo progettato per supportare le immagini, ma l'idea di base di cosa significa incollare un elemento rimane lo stesso.  La logica di comando non può essere fornita dal comando, bensì dal controllo o dall'applicazione.  
  
 Molti controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispongono del supporto incorporato per alcuni comandi della libreria di comandi.  <xref:System.Windows.Controls.TextBox>, ad esempio, supporta molti dei comandi di modifica dell'applicazione, ad esempio <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, e <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Lo sviluppatore dell'applicazione non deve eseguire operazioni particolari per garantire il funzionamento di questi comandi con tali controlli.  Se il <xref:System.Windows.Controls.TextBox> è la destinazione di comando quando viene eseguito il comando, gestirà il comando utilizzando il <xref:System.Windows.Input.CommandBinding> che è incorporato nel controllo.  
  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Controls.MenuItem> come l'origine del comando per il <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando, in cui un <xref:System.Windows.Controls.TextBox> è la destinazione del comando.  Tutta la logica che definisce il modo in <xref:System.Windows.Controls.TextBox> esegue Incolla è incorporata il <xref:System.Windows.Controls.TextBox> controllo.  
  
 Oggetto <xref:System.Windows.Controls.MenuItem> viene creato ed è <xref:System.Windows.Controls.MenuItem.Command%2A> è impostata sul <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando.  Il <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> non è impostata esplicitamente sul <xref:System.Windows.Controls.TextBox> oggetto.  Quando il <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> non è impostata, la destinazione per il comando è l'elemento che lo stato attivo.  Se l'elemento che lo stato attivo non supporta il <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comandi oppure attualmente non è possibile eseguire il comando Incolla (ad esempio, negli Appunti sono vuoto,) il <xref:System.Windows.Controls.MenuItem> verrebbe visualizzato in grigio.  
  
 [!code-xaml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Associare un comando a un controllo senza supporto del comando](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)
