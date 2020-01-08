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
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="d654a-102">Procedura: implementare ICommandSource</span><span class="sxs-lookup"><span data-stu-id="d654a-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="d654a-103">Questo esempio illustra come creare un'origine comando implementando <xref:System.Windows.Input.ICommandSource>.</span><span class="sxs-lookup"><span data-stu-id="d654a-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="d654a-104">Un'origine comando è un oggetto che sa come richiamare un comando.</span><span class="sxs-lookup"><span data-stu-id="d654a-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="d654a-105">L'interfaccia <xref:System.Windows.Input.ICommandSource> espone tre membri:</span><span class="sxs-lookup"><span data-stu-id="d654a-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="d654a-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: comando che verrà richiamato.</span><span class="sxs-lookup"><span data-stu-id="d654a-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="d654a-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: tipo di dati definito dall'utente che viene passato dall'origine del comando al metodo che gestisce il comando.</span><span class="sxs-lookup"><span data-stu-id="d654a-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="d654a-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: oggetto in cui viene eseguito il comando.</span><span class="sxs-lookup"><span data-stu-id="d654a-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="d654a-109">In questo esempio viene creata una classe che eredita dal controllo <xref:System.Windows.Controls.Slider> e implementa l'interfaccia <xref:System.Windows.Input.ICommandSource>.</span><span class="sxs-lookup"><span data-stu-id="d654a-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="d654a-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d654a-110">Example</span></span>

<span data-ttu-id="d654a-111">WPF offre una serie di classi che implementano <xref:System.Windows.Input.ICommandSource>, ad esempio <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>e <xref:System.Windows.Documents.Hyperlink>.</span><span class="sxs-lookup"><span data-stu-id="d654a-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="d654a-112">Un'origine comando definisce il modo in cui richiama un comando.</span><span class="sxs-lookup"><span data-stu-id="d654a-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="d654a-113">Queste classi richiamano un comando quando vengono selezionate e diventano solo un'origine di comando quando viene impostata la relativa proprietà <xref:System.Windows.Input.ICommandSource.Command%2A>.</span><span class="sxs-lookup"><span data-stu-id="d654a-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="d654a-114">In questo esempio verrà richiamato il comando quando il dispositivo di scorrimento viene spostato o più accuratamente quando viene modificata la proprietà <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="d654a-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="d654a-115">Di seguito è riportata la definizione della classe:</span><span class="sxs-lookup"><span data-stu-id="d654a-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="d654a-116">Il passaggio successivo consiste nell'implementare i membri <xref:System.Windows.Input.ICommandSource>.</span><span class="sxs-lookup"><span data-stu-id="d654a-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="d654a-117">In questo esempio, le proprietà vengono implementate come oggetti <xref:System.Windows.DependencyProperty>.</span><span class="sxs-lookup"><span data-stu-id="d654a-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="d654a-118">Questo consente alle proprietà di utilizzare data binding.</span><span class="sxs-lookup"><span data-stu-id="d654a-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="d654a-119">Per ulteriori informazioni sulla classe <xref:System.Windows.DependencyProperty>, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d654a-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="d654a-120">Per ulteriori informazioni su data binding, vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d654a-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="d654a-121">Qui viene mostrata solo la proprietà <xref:System.Windows.Input.ICommandSource.Command%2A>.</span><span class="sxs-lookup"><span data-stu-id="d654a-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>
 
[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="d654a-122">Di seguito è riportato il callback di modifica <xref:System.Windows.DependencyProperty>:</span><span class="sxs-lookup"><span data-stu-id="d654a-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="d654a-123">Il passaggio successivo consiste nell'aggiungere e rimuovere il comando associato all'origine del comando.</span><span class="sxs-lookup"><span data-stu-id="d654a-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="d654a-124">Non è possibile sovrascrivere la proprietà <xref:System.Windows.Input.ICommandSource.Command%2A> quando viene aggiunto un nuovo comando, perché i gestori eventi associati al comando precedente, se presente, devono essere rimossi per primi.</span><span class="sxs-lookup"><span data-stu-id="d654a-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="d654a-125">Il passaggio successivo consiste nel creare la logica per il gestore <xref:System.Windows.Input.ICommand.CanExecuteChanged>.</span><span class="sxs-lookup"><span data-stu-id="d654a-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="d654a-126">L'evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> notifica all'origine del comando che è possibile che la capacità del comando da eseguire sulla destinazione corrente del comando sia stata modificata.</span><span class="sxs-lookup"><span data-stu-id="d654a-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="d654a-127">Quando l'origine di un comando riceve questo evento, in genere chiama il metodo <xref:System.Windows.Input.ICommand.CanExecute%2A> sul comando.</span><span class="sxs-lookup"><span data-stu-id="d654a-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="d654a-128">Se non è possibile eseguire il comando sulla destinazione del comando corrente, l'origine comando si disabilita in genere.</span><span class="sxs-lookup"><span data-stu-id="d654a-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="d654a-129">Se il comando può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere lo Abilita.</span><span class="sxs-lookup"><span data-stu-id="d654a-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="d654a-130">L'ultimo passaggio è il metodo <xref:System.Windows.Input.ICommand.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="d654a-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="d654a-131">Se il comando è un <xref:System.Windows.Input.RoutedCommand>, viene chiamato il metodo <xref:System.Windows.Input.RoutedCommand.Execute%2A> <xref:System.Windows.Input.RoutedCommand>; in caso contrario, viene chiamato il metodo <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="d654a-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="d654a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d654a-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="d654a-133">Panoramica sull'esecuzione di comandi</span><span class="sxs-lookup"><span data-stu-id="d654a-133">Commanding Overview</span></span>](commanding-overview.md)
