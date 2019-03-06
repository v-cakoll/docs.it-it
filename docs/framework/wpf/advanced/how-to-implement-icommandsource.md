---
title: "Procedura: Implementare l'oggetto ICommandSource"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 42395d2916d58b2119cfe41ca154f258c3b0ec58
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361460"
---
# <a name="how-to-implement-icommandsource"></a>Procedura: Implementare l'oggetto ICommandSource
Questo esempio illustra come creare un'origine del comando implementando <xref:System.Windows.Input.ICommandSource>.  Un comando di origine è un oggetto che sa come richiamare un comando.  Il <xref:System.Windows.Input.ICommandSource> interfaccia espone tre membri: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>, e <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.  <xref:System.Windows.Input.ICommandSource.Command%2A> è il comando che verrà richiamato. Il <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> è un tipo di dati definito dall'utente che viene passato al metodo che gestisce il comando dall'origine comando. Il <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> è l'oggetto che viene eseguito il comando.  
  
 In questo esempio viene creata una classe che crea una sottoclasse di <xref:System.Windows.Controls.Slider> controllo e implementa <xref:System.Windows.Input.ICommandSource>.  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce una serie di classi che implementano <xref:System.Windows.Input.ICommandSource>, ad esempio <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, e <xref:System.Windows.Controls.ListBoxItem>.  Un'origine del comando consente di definire come richiama un comando.   <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.MenuItem> richiamare un comando quando vengono selezionati.  Oggetto <xref:System.Windows.Controls.ListBoxItem> richiama un comando quando si fa doppio. Queste classi diventano solo un comando di origine dopo l'evento loro <xref:System.Windows.Input.ICommandSource.Command%2A> è impostata.  
  
 In questo esempio, il comando viene richiamato quando il dispositivo di scorrimento viene spostata, o, più precisamente, quando il <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> proprietà viene modificata.  
  
 Di seguito è la definizione della classe.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 Il passaggio successivo consiste nell'implementare il <xref:System.Windows.Input.ICommandSource> membri.  In questo esempio, le proprietà vengono implementate come <xref:System.Windows.DependencyProperty> oggetti.  In questo modo le proprietà da utilizzare l'associazione dati.  Per altre informazioni sul <xref:System.Windows.DependencyProperty> classe, vedere la [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md).  Per altre informazioni sul data binding, vedere la [Panoramica sul Data Binding](../data/data-binding-overview.md).  
  
 Solo il <xref:System.Windows.Input.ICommandSource.Command%2A> viene mostrata di seguito.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 Di seguito è riportato il <xref:System.Windows.DependencyProperty> callback di modifica.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 Il passaggio successivo è di aggiungere e rimuovere il comando che è associato l'origine del comando.  Il <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà non può semplicemente essere sovrascritto quando viene aggiunto un nuovo comando, perché i gestori eventi associati con il comando precedente, se si è verificato uno, devono essere rimosse per prime.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 L'ultimo passaggio consiste nel creare la logica per la <xref:System.Windows.Input.ICommand.CanExecuteChanged> gestore e <xref:System.Windows.Input.ICommand.Execute%2A> (metodo).  
  
 Il <xref:System.Windows.Input.ICommand.CanExecuteChanged> evento informa l'origine del comando potrebbe aver modificato la capacità del comando per eseguire il comando sulla destinazione corrente.  Quando un comando di origine riceve questo evento, in genere chiama il <xref:System.Windows.Input.ICommand.CanExecute%2A> metodo sul comando.  Se non è possibile eseguire il comando sulla destinazione del comando corrente, l'origine del comando in genere si disabilita automaticamente.  Se il comando può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere si attiva.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 L'ultimo passaggio prevede la <xref:System.Windows.Input.ICommand.Execute%2A> (metodo).  Se il comando è un <xref:System.Windows.Input.RoutedCommand>, il <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> viene chiamato metodo; in caso contrario, il <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> viene chiamato il metodo.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Panoramica sull'esecuzione di comandi](commanding-overview.md)
