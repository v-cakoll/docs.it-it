---
title: 'Procedura: creare un oggetto RoutedCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: 75e6c435516fe2a174cf991bd41f24e1b30a212a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544109"
---
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="62f40-102">Procedura: creare un oggetto RoutedCommand</span><span class="sxs-lookup"><span data-stu-id="62f40-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="62f40-103">In questo esempio viene illustrato come creare un oggetto personalizzato <xref:System.Windows.Input.RoutedCommand> e come implementare il comando personalizzato creando una <xref:System.Windows.Input.ExecutedRoutedEventHandler> e <xref:System.Windows.Input.CanExecuteRoutedEventHandler> e associarle a un <xref:System.Windows.Input.CommandBinding>.</span><span class="sxs-lookup"><span data-stu-id="62f40-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="62f40-104">Per ulteriori informazioni sui comandi, vedere il [panoramica dei comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62f40-104">For more information on commanding, see the [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62f40-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="62f40-105">Example</span></span>  
 <span data-ttu-id="62f40-106">Il primo passaggio nella creazione di un <xref:System.Windows.Input.RoutedCommand> è la definizione di comando e istanza.</span><span class="sxs-lookup"><span data-stu-id="62f40-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="62f40-107">Per utilizzare il comando in un'applicazione, è necessario creare i gestori di eventi che consentono di definire il comando non</span><span class="sxs-lookup"><span data-stu-id="62f40-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="62f40-108">Successivamente, un <xref:System.Windows.Input.CommandBinding> viene creato il comando che associa i gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="62f40-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="62f40-109">Il <xref:System.Windows.Input.CommandBinding> viene creato in un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="62f40-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="62f40-110">Questo oggetto definisce l'ambito del <xref:System.Windows.Input.CommandBinding> nell'albero degli elementi</span><span class="sxs-lookup"><span data-stu-id="62f40-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="62f40-111">Il passaggio finale consiste nel richiamare il comando.</span><span class="sxs-lookup"><span data-stu-id="62f40-111">The final step is invoking the command.</span></span>  <span data-ttu-id="62f40-112">Per richiamare un comando è possibile associarlo a un <xref:System.Windows.Input.ICommandSource>, ad esempio un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="62f40-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="62f40-113">Quando si fa clic sul pulsante, il <xref:System.Windows.Input.RoutedCommand.Execute%2A> metodo personalizzato <xref:System.Windows.Input.RoutedCommand> viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="62f40-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="62f40-114">Il <xref:System.Windows.Input.RoutedCommand> genera il <xref:System.Windows.Input.CommandManager.PreviewExecuted> e <xref:System.Windows.Input.CommandManager.Executed> gli eventi indirizzati.</span><span class="sxs-lookup"><span data-stu-id="62f40-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="62f40-115">Questi eventi attraversano l'albero degli elementi cercando un <xref:System.Windows.Input.CommandBinding> per questo comando particolare.</span><span class="sxs-lookup"><span data-stu-id="62f40-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="62f40-116">Se un <xref:System.Windows.Input.CommandBinding> viene trovato, il <xref:System.Windows.Input.ExecutedRoutedEventHandler> associato <xref:System.Windows.Input.CommandBinding> viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="62f40-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f40-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62f40-117">See Also</span></span>  
 <xref:System.Windows.Input.RoutedCommand>  
 [<span data-ttu-id="62f40-118">Panoramica sull'esecuzione di comandi</span><span class="sxs-lookup"><span data-stu-id="62f40-118">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)
