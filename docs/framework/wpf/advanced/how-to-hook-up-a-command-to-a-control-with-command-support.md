---
title: 'Procedura: Associare un comando a un controllo con supporto dei comandi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
ms.openlocfilehash: 4eded4812d8894b58331f26ec75c592c15e95419
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663206"
---
# <a name="how-to-hook-up-a-command-to-a-control-with-command-support"></a>Procedura: Associare un comando a un controllo con supporto dei comandi
Nell'esempio seguente viene illustrato come associare una classe <xref:System.Windows.Input.RoutedCommand> a una classe <xref:System.Windows.Controls.Control> che dispone del supporto incorporato per il comando.  Per un esempio completo in cui i comandi sono associati a più origini, vedere l'esempio [Create a Custom RoutedCommand Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand) (Creare un esempio di oggetto RoutedCommand personalizzato).  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce una libreria di comandi comuni usati regolarmente dai programmatori di applicazioni.  Le classi che costituiscono la libreria del comando sono: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> e <xref:System.Windows.Documents.EditingCommands>.  
  
 Gli oggetti <xref:System.Windows.Input.RoutedCommand> statici che costituiscono queste classi non forniscono la logica per il comando.  La logica per il comando è associata al comando con un <xref:System.Windows.Input.CommandBinding>.  Alcuni controlli dispongono di CommandBinding incorporati per determinati comandi.  Questo meccanismo consente di mantenere invariata la semantica di un comando, mentre l'implementazione effettiva può cambiare.  Un oggetto <xref:System.Windows.Controls.TextBox>, ad esempio, gestisce il comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> in modo diverso rispetto a un controllo progettato per supportare immagini, ma l'idea alla base dell'operazione di incollamento rimane invariata.  La logica di comando non può essere fornita dal comando, bensì dal controllo o dall'applicazione.  
  
 Molti controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispongono del supporto incorporato per alcuni comandi della libreria di comandi.  <xref:System.Windows.Controls.TextBox>, ad esempio, supporta molti dei comandi di modifica dell'applicazione, ad esempio <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> e <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Lo sviluppatore dell'applicazione non deve eseguire operazioni particolari per garantire il funzionamento di questi comandi con tali controlli.  Se la destinazione del comando eseguito è <xref:System.Windows.Controls.TextBox>, il comando verrà gestito utilizzando il <xref:System.Windows.Input.CommandBinding> incorporato nel controllo.  
  
 Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Windows.Controls.MenuItem> come origine del comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> in cui <xref:System.Windows.Controls.TextBox> è la destinazione del comando.  Tutta la logica che definisce il modo in cui <xref:System.Windows.Controls.TextBox> esegue Incolla è incorporata nel controllo <xref:System.Windows.Controls.TextBox>.  
  
 Viene creata una classe <xref:System.Windows.Controls.MenuItem> e la relativa proprietà <xref:System.Windows.Controls.MenuItem.Command%2A> è impostata sul comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  La proprietà <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> non è impostata esplicitamente sull'oggetto <xref:System.Windows.Controls.TextBox>.  Quando <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> non è impostata, la destinazione per il comando è l'elemento con lo stato attivo della tastiera.  Se l'elemento con lo stato attivo della tastiera non supporta il comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> oppure non è attualmente in grado di eseguire il comando Incolla, ad esempio gli Appunti sono vuoti, <xref:System.Windows.Controls.MenuItem> viene visualizzato in grigio.  
  
 [!code-xaml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md)
- [Associare un comando a un controllo senza supporto del comando](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)
