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
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="51bf2-102">Procedura: implementare ICommandSource</span><span class="sxs-lookup"><span data-stu-id="51bf2-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="51bf2-103">In questo esempio viene illustrato come <xref:System.Windows.Input.ICommandSource>creare un'origine comando implementando .</span><span class="sxs-lookup"><span data-stu-id="51bf2-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="51bf2-104">Un'origine comando è un oggetto che sa come richiamare un comando.</span><span class="sxs-lookup"><span data-stu-id="51bf2-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="51bf2-105">L'interfaccia espone tre membri:The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span><span class="sxs-lookup"><span data-stu-id="51bf2-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="51bf2-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: il comando che verrà richiamato.</span><span class="sxs-lookup"><span data-stu-id="51bf2-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="51bf2-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: un tipo di dati definito dall'utente che viene passato dall'origine del comando al metodo che gestisce il comando.</span><span class="sxs-lookup"><span data-stu-id="51bf2-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="51bf2-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: l'oggetto su cui viene eseguito il comando.</span><span class="sxs-lookup"><span data-stu-id="51bf2-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="51bf2-109">In questo esempio viene creata una classe <xref:System.Windows.Controls.Slider> che eredita <xref:System.Windows.Input.ICommandSource> dal controllo e implementa l'interfaccia .</span><span class="sxs-lookup"><span data-stu-id="51bf2-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="51bf2-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="51bf2-110">Example</span></span>

<span data-ttu-id="51bf2-111">WPFWPF fornisce un numero <xref:System.Windows.Input.ICommandSource>di <xref:System.Windows.Controls.Button>classi <xref:System.Windows.Controls.MenuItem>che <xref:System.Windows.Documents.Hyperlink>implementano , ad esempio , e .</span><span class="sxs-lookup"><span data-stu-id="51bf2-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="51bf2-112">Un'origine comando definisce come richiama un comando.</span><span class="sxs-lookup"><span data-stu-id="51bf2-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="51bf2-113">Queste classi richiamano un comando quando si fa clic su <xref:System.Windows.Input.ICommandSource.Command%2A> di esse e diventano un'origine comando solo quando la relativa proprietà è impostata.</span><span class="sxs-lookup"><span data-stu-id="51bf2-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="51bf2-114">In questo esempio, si richiamerà il comando quando il dispositivo <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> di scorrimento viene spostato o, più precisamente, quando la proprietà viene modificata.</span><span class="sxs-lookup"><span data-stu-id="51bf2-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="51bf2-115">Di seguito è riportata la definizione della classe:The following is the class definition:</span><span class="sxs-lookup"><span data-stu-id="51bf2-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="51bf2-116">Il passaggio successivo <xref:System.Windows.Input.ICommandSource> consiste nell'implementare i membri.</span><span class="sxs-lookup"><span data-stu-id="51bf2-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="51bf2-117">In questo esempio, le <xref:System.Windows.DependencyProperty> proprietà vengono implementate come oggetti.</span><span class="sxs-lookup"><span data-stu-id="51bf2-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="51bf2-118">Ciò consente alle proprietà di utilizzare l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="51bf2-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="51bf2-119">Per ulteriori informazioni <xref:System.Windows.DependencyProperty> sulla classe, vedere [Cenni](dependency-properties-overview.md)preliminari sulle proprietà di dipendenza .</span><span class="sxs-lookup"><span data-stu-id="51bf2-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="51bf2-120">Per ulteriori informazioni sull'associazione dati, vedere Cenni preliminari [sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="51bf2-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="51bf2-121">Qui <xref:System.Windows.Input.ICommandSource.Command%2A> viene mostrata solo la proprietà.</span><span class="sxs-lookup"><span data-stu-id="51bf2-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="51bf2-122">Di seguito <xref:System.Windows.DependencyProperty> è riportato il callback delle modifiche:The following is the change callback:</span><span class="sxs-lookup"><span data-stu-id="51bf2-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="51bf2-123">Il passaggio successivo consiste nell'aggiungere e rimuovere il comando associato all'origine del comando.</span><span class="sxs-lookup"><span data-stu-id="51bf2-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="51bf2-124">La <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà non può essere semplicemente sovrascritta quando viene aggiunto un nuovo comando, perché i gestori eventi associati al comando precedente, se presente, devono essere rimossi per primi.</span><span class="sxs-lookup"><span data-stu-id="51bf2-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="51bf2-125">Il passaggio successivo consiste <xref:System.Windows.Input.ICommand.CanExecuteChanged> nel creare la logica per il gestore.</span><span class="sxs-lookup"><span data-stu-id="51bf2-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="51bf2-126">L'evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> notifica all'origine del comando che la capacità del comando di eseguire sulla destinazione del comando corrente potrebbe essere stata modificata.</span><span class="sxs-lookup"><span data-stu-id="51bf2-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="51bf2-127">Quando un'origine comando riceve questo evento, in genere chiama il <xref:System.Windows.Input.ICommand.CanExecute%2A> metodo sul comando.</span><span class="sxs-lookup"><span data-stu-id="51bf2-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="51bf2-128">Se il comando non può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere si disabilita.</span><span class="sxs-lookup"><span data-stu-id="51bf2-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="51bf2-129">Se il comando può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere si abiliterà.</span><span class="sxs-lookup"><span data-stu-id="51bf2-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="51bf2-130">L'ultimo passaggio è il <xref:System.Windows.Input.ICommand.Execute%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="51bf2-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="51bf2-131">Se il comando <xref:System.Windows.Input.RoutedCommand>è <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> un , viene chiamato il metodo ; in caso <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> contrario, viene chiamato il metodo .</span><span class="sxs-lookup"><span data-stu-id="51bf2-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="51bf2-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51bf2-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="51bf2-133">Cenni preliminari sull'esecuzione di comandi</span><span class="sxs-lookup"><span data-stu-id="51bf2-133">Commanding Overview</span></span>](commanding-overview.md)
