---
title: 'Procedura: implementare ICommandSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 974b145a125a158bcafff93f8e9bc11001e00bf1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453589"
---
# <a name="how-to-implement-icommandsource"></a>Procedura: implementare ICommandSource
Questo esempio illustra come creare un'origine comando implementando <xref:System.Windows.Input.ICommandSource>.  Un'origine comando è un oggetto che sa come richiamare un comando.  L'interfaccia <xref:System.Windows.Input.ICommandSource> espone tre membri: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>e <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.  <xref:System.Windows.Input.ICommandSource.Command%2A> è il comando che verrà richiamato. Il <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> è un tipo di dati definito dall'utente che viene passato dall'origine del comando al metodo che gestisce il comando. Il <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> è l'oggetto su cui viene eseguito il comando.  
  
 In questo esempio viene creata una classe che esegue la sottoclasse del controllo <xref:System.Windows.Controls.Slider> e implementa <xref:System.Windows.Input.ICommandSource>.  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un numero di classi che implementano <xref:System.Windows.Input.ICommandSource>, ad esempio <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>e <xref:System.Windows.Controls.ListBoxItem>.  Un'origine comando definisce il modo in cui richiama un comando.   <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.MenuItem> richiamare un comando quando vengono selezionate.  Un <xref:System.Windows.Controls.ListBoxItem> richiama un comando quando viene fatto doppio clic. Queste classi diventano solo un'origine di comando quando viene impostata la relativa proprietà <xref:System.Windows.Input.ICommandSource.Command%2A>.  
  
 Per questo esempio verrà richiamato il comando quando il dispositivo di scorrimento viene spostato o con maggiore precisione quando viene modificata la proprietà <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.  
  
 Di seguito è riportata la definizione della classe.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 Il passaggio successivo consiste nell'implementare i membri <xref:System.Windows.Input.ICommandSource>.  In questo esempio, le proprietà vengono implementate come oggetti <xref:System.Windows.DependencyProperty>.  Questo consente alle proprietà di utilizzare data binding.  Per ulteriori informazioni sulla classe <xref:System.Windows.DependencyProperty>, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md).  Per ulteriori informazioni su data binding, vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).  
  
 Qui viene mostrata solo la proprietà <xref:System.Windows.Input.ICommandSource.Command%2A>.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 Di seguito è riportato il <xref:System.Windows.DependencyProperty> callback di modifica.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 Il passaggio successivo consiste nell'aggiungere e rimuovere il comando associato all'origine del comando.  Non è possibile sovrascrivere la proprietà <xref:System.Windows.Input.ICommandSource.Command%2A> quando viene aggiunto un nuovo comando, perché i gestori eventi associati al comando precedente, se presente, devono essere rimossi per primi.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 L'ultimo passaggio consiste nel creare la logica per il gestore <xref:System.Windows.Input.ICommand.CanExecuteChanged> e il <xref:System.Windows.Input.ICommand.Execute%2A> metodo.  
  
 L'evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> notifica all'origine del comando che è possibile che la capacità del comando da eseguire sulla destinazione corrente del comando sia stata modificata.  Quando l'origine di un comando riceve questo evento, in genere chiama il metodo <xref:System.Windows.Input.ICommand.CanExecute%2A> sul comando.  Se non è possibile eseguire il comando sulla destinazione del comando corrente, l'origine comando si disabilita in genere.  Se il comando può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere lo Abilita.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 L'ultimo passaggio è il metodo <xref:System.Windows.Input.ICommand.Execute%2A>.  Se il comando è un <xref:System.Windows.Input.RoutedCommand>, viene chiamato il metodo <xref:System.Windows.Input.RoutedCommand.Execute%2A> <xref:System.Windows.Input.RoutedCommand>; in caso contrario, viene chiamato il metodo <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A>.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Panoramica sull'esecuzione di comandi](commanding-overview.md)
