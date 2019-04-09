---
title: 'Procedura: Creare un oggetto RoutedCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: d433658a3039c262d2f682eff09df646d978018c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109044"
---
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="97bce-102">Procedura: Creare un oggetto RoutedCommand</span><span class="sxs-lookup"><span data-stu-id="97bce-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="97bce-103">Questo esempio viene illustrato come creare una classe personalizzata <xref:System.Windows.Input.RoutedCommand> e come implementare il comando personalizzato tramite la creazione di un <xref:System.Windows.Input.ExecutedRoutedEventHandler> e una <xref:System.Windows.Input.CanExecuteRoutedEventHandler> e il ricollegamento di un <xref:System.Windows.Input.CommandBinding>.</span><span class="sxs-lookup"><span data-stu-id="97bce-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="97bce-104">Per altre informazioni sull'esecuzione di comandi, vedere la [Cenni preliminari](commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="97bce-104">For more information on commanding, see the [Commanding Overview](commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="97bce-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="97bce-105">Example</span></span>  
 <span data-ttu-id="97bce-106">Il primo passaggio nella creazione di un <xref:System.Windows.Input.RoutedCommand> è la definizione di comando e crearne un'istanza.</span><span class="sxs-lookup"><span data-stu-id="97bce-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="97bce-107">Per usare il comando in un'applicazione, è necessario creare i gestori di eventi che definiscono il comando non</span><span class="sxs-lookup"><span data-stu-id="97bce-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="97bce-108">Successivamente, un <xref:System.Windows.Input.CommandBinding> viene creato il comando che associa i gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="97bce-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="97bce-109">Il <xref:System.Windows.Input.CommandBinding> viene creato in un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="97bce-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="97bce-110">Questo oggetto definisce l'ambito del <xref:System.Windows.Input.CommandBinding> nell'albero degli elementi</span><span class="sxs-lookup"><span data-stu-id="97bce-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="97bce-111">Il passaggio finale consiste nel richiamare il comando.</span><span class="sxs-lookup"><span data-stu-id="97bce-111">The final step is invoking the command.</span></span>  <span data-ttu-id="97bce-112">Un modo per richiamare un comando consiste nell'associare a un <xref:System.Windows.Input.ICommandSource>, ad esempio un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="97bce-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="97bce-113">Quando si fa clic sul pulsante, il <xref:System.Windows.Input.RoutedCommand.Execute%2A> metodo sull'oggetto personalizzato <xref:System.Windows.Input.RoutedCommand> viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="97bce-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="97bce-114">Il <xref:System.Windows.Input.RoutedCommand> genera il <xref:System.Windows.Input.CommandManager.PreviewExecuted> e <xref:System.Windows.Input.CommandManager.Executed> eventi indirizzati.</span><span class="sxs-lookup"><span data-stu-id="97bce-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="97bce-115">Questi eventi attraversano l'albero degli elementi cercando un <xref:System.Windows.Input.CommandBinding> per questo particolare comando.</span><span class="sxs-lookup"><span data-stu-id="97bce-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="97bce-116">Se un <xref:System.Windows.Input.CommandBinding> viene trovato, il <xref:System.Windows.Input.ExecutedRoutedEventHandler> associati <xref:System.Windows.Input.CommandBinding> viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="97bce-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97bce-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97bce-117">See also</span></span>

- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="97bce-118">Cenni preliminari sull'esecuzione di comandi</span><span class="sxs-lookup"><span data-stu-id="97bce-118">Commanding Overview</span></span>](commanding-overview.md)
