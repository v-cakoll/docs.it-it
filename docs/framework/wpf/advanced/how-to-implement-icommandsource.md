---
title: 'Procedura: implementare ICommandSource'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 6c18e0b77ec53d9bd3e7ce610f2940effe603c88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174693"
---
# <a name="how-to-implement-icommandsource"></a>Procedura: implementare ICommandSource

In questo esempio viene illustrato come <xref:System.Windows.Input.ICommandSource>creare un'origine comando implementando . Un'origine comando è un oggetto che sa come richiamare un comando. L'interfaccia espone tre membri:The <xref:System.Windows.Input.ICommandSource> interface exposes three members:

- <xref:System.Windows.Input.ICommandSource.Command%2A>: il comando che verrà richiamato.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: un tipo di dati definito dall'utente che viene passato dall'origine del comando al metodo che gestisce il comando.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: l'oggetto su cui viene eseguito il comando.

In questo esempio viene creata una classe <xref:System.Windows.Controls.Slider> che eredita <xref:System.Windows.Input.ICommandSource> dal controllo e implementa l'interfaccia .
  
## <a name="example"></a>Esempio

WPFWPF fornisce un numero <xref:System.Windows.Input.ICommandSource>di <xref:System.Windows.Controls.Button>classi <xref:System.Windows.Controls.MenuItem>che <xref:System.Windows.Documents.Hyperlink>implementano , ad esempio , e . Un'origine comando definisce come richiama un comando. Queste classi richiamano un comando quando si fa clic su <xref:System.Windows.Input.ICommandSource.Command%2A> di esse e diventano un'origine comando solo quando la relativa proprietà è impostata.

In questo esempio, si richiamerà il comando quando il dispositivo <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> di scorrimento viene spostato o, più precisamente, quando la proprietà viene modificata.

Di seguito è riportata la definizione della classe:The following is the class definition:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

Il passaggio successivo <xref:System.Windows.Input.ICommandSource> consiste nell'implementare i membri. In questo esempio, le <xref:System.Windows.DependencyProperty> proprietà vengono implementate come oggetti. Ciò consente alle proprietà di utilizzare l'associazione dati. Per ulteriori informazioni <xref:System.Windows.DependencyProperty> sulla classe, vedere [Cenni](dependency-properties-overview.md)preliminari sulle proprietà di dipendenza . Per ulteriori informazioni sull'associazione dati, vedere Cenni preliminari [sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).

Qui <xref:System.Windows.Input.ICommandSource.Command%2A> viene mostrata solo la proprietà.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
Di seguito <xref:System.Windows.DependencyProperty> è riportato il callback delle modifiche:The following is the change callback:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

Il passaggio successivo consiste nell'aggiungere e rimuovere il comando associato all'origine del comando. La <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà non può essere semplicemente sovrascritta quando viene aggiunto un nuovo comando, perché i gestori eventi associati al comando precedente, se presente, devono essere rimossi per primi.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

Il passaggio successivo consiste <xref:System.Windows.Input.ICommand.CanExecuteChanged> nel creare la logica per il gestore.

L'evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> notifica all'origine del comando che la capacità del comando di eseguire sulla destinazione del comando corrente potrebbe essere stata modificata. Quando un'origine comando riceve questo evento, in genere chiama il <xref:System.Windows.Input.ICommand.CanExecute%2A> metodo sul comando. Se il comando non può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere si disabilita. Se il comando può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere si abiliterà.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

L'ultimo passaggio è il <xref:System.Windows.Input.ICommand.Execute%2A> metodo. Se il comando <xref:System.Windows.Input.RoutedCommand>è <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> un , viene chiamato il metodo ; in caso <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> contrario, viene chiamato il metodo .

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md)
