---
title: 'Procedura: implementare ICommandSource'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 755377d25a2deb48aa9da86d4182075e30763530
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345089"
---
# <a name="how-to-implement-icommandsource"></a>Procedura: implementare ICommandSource

Questo esempio illustra come creare un'origine comando implementando <xref:System.Windows.Input.ICommandSource>. Un'origine comando è un oggetto che sa come richiamare un comando. L'interfaccia <xref:System.Windows.Input.ICommandSource> espone tre membri:

- <xref:System.Windows.Input.ICommandSource.Command%2A>: comando che verrà richiamato.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: tipo di dati definito dall'utente che viene passato dall'origine del comando al metodo che gestisce il comando.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: oggetto in cui viene eseguito il comando.

In questo esempio viene creata una classe che eredita dal controllo <xref:System.Windows.Controls.Slider> e implementa l'interfaccia <xref:System.Windows.Input.ICommandSource>.
  
## <a name="example"></a>Esempio

WPF offre una serie di classi che implementano <xref:System.Windows.Input.ICommandSource>, ad esempio <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>e <xref:System.Windows.Documents.Hyperlink>. Un'origine comando definisce il modo in cui richiama un comando. Queste classi richiamano un comando quando vengono selezionate e diventano solo un'origine di comando quando viene impostata la relativa proprietà <xref:System.Windows.Input.ICommandSource.Command%2A>.

In questo esempio verrà richiamato il comando quando il dispositivo di scorrimento viene spostato o più accuratamente quando viene modificata la proprietà <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.

Di seguito è riportata la definizione della classe:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

Il passaggio successivo consiste nell'implementare i membri <xref:System.Windows.Input.ICommandSource>. In questo esempio, le proprietà vengono implementate come oggetti <xref:System.Windows.DependencyProperty>. Questo consente alle proprietà di utilizzare data binding. Per ulteriori informazioni sulla classe <xref:System.Windows.DependencyProperty>, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md). Per ulteriori informazioni su data binding, vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).

Qui viene mostrata solo la proprietà <xref:System.Windows.Input.ICommandSource.Command%2A>.
 
[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
Di seguito è riportato il callback di modifica <xref:System.Windows.DependencyProperty>:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

Il passaggio successivo consiste nell'aggiungere e rimuovere il comando associato all'origine del comando. Non è possibile sovrascrivere la proprietà <xref:System.Windows.Input.ICommandSource.Command%2A> quando viene aggiunto un nuovo comando, perché i gestori eventi associati al comando precedente, se presente, devono essere rimossi per primi.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

Il passaggio successivo consiste nel creare la logica per il gestore <xref:System.Windows.Input.ICommand.CanExecuteChanged>.

L'evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> notifica all'origine del comando che è possibile che la capacità del comando da eseguire sulla destinazione corrente del comando sia stata modificata. Quando l'origine di un comando riceve questo evento, in genere chiama il metodo <xref:System.Windows.Input.ICommand.CanExecute%2A> sul comando. Se non è possibile eseguire il comando sulla destinazione del comando corrente, l'origine comando si disabilita in genere. Se il comando può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere lo Abilita.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

L'ultimo passaggio è il metodo <xref:System.Windows.Input.ICommand.Execute%2A>. Se il comando è un <xref:System.Windows.Input.RoutedCommand>, viene chiamato il metodo <xref:System.Windows.Input.RoutedCommand.Execute%2A> <xref:System.Windows.Input.RoutedCommand>; in caso contrario, viene chiamato il metodo <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A>.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Panoramica sull'esecuzione di comandi](commanding-overview.md)
