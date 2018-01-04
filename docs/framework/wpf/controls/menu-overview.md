---
title: Cenni preliminari sulla classe Menu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ab5092b1bc9db22390a18b2c1cb1ad5725a2037
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="menu-overview"></a><span data-ttu-id="0109c-102">Cenni preliminari sulla classe Menu</span><span class="sxs-lookup"><span data-stu-id="0109c-102">Menu Overview</span></span>
<span data-ttu-id="0109c-103">La <xref:System.Windows.Controls.Menu> classe consente di organizzare gli elementi associati a comandi e gestori eventi in ordine gerarchico.</span><span class="sxs-lookup"><span data-stu-id="0109c-103">The <xref:System.Windows.Controls.Menu> class enables you to organize elements associated with commands and event handlers in a hierarchical order.</span></span> <span data-ttu-id="0109c-104">Ogni <xref:System.Windows.Controls.Menu> elemento contiene una raccolta di <xref:System.Windows.Controls.MenuItem> elementi.</span><span class="sxs-lookup"><span data-stu-id="0109c-104">Each <xref:System.Windows.Controls.Menu> element contains a collection of <xref:System.Windows.Controls.MenuItem> elements.</span></span>  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a><span data-ttu-id="0109c-105">Controllo Menu</span><span class="sxs-lookup"><span data-stu-id="0109c-105">Menu Control</span></span>  
 <span data-ttu-id="0109c-106">Il <xref:System.Windows.Controls.Menu> consente di visualizzare un elenco di elementi che specificano le opzioni per un'applicazione o i comandi.</span><span class="sxs-lookup"><span data-stu-id="0109c-106">The <xref:System.Windows.Controls.Menu> control presents a list of items that specify commands or options for an application.</span></span> <span data-ttu-id="0109c-107">In genere, facendo clic su un <xref:System.Windows.Controls.MenuItem> viene aperto un sottomenu o fa sì che un'applicazione eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="0109c-107">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a><span data-ttu-id="0109c-108">Creazione di menu</span><span class="sxs-lookup"><span data-stu-id="0109c-108">Creating Menus</span></span>  
 <span data-ttu-id="0109c-109">Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Menu> per modificare il testo in un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="0109c-109">The following example creates a <xref:System.Windows.Controls.Menu> to manipulate text in a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="0109c-110">Il <xref:System.Windows.Controls.Menu> contiene <xref:System.Windows.Controls.MenuItem> gli oggetti che utilizzano il <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, e <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà e <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, e <xref:System.Windows.Controls.MenuItem.Click> eventi.</span><span class="sxs-lookup"><span data-stu-id="0109c-110">The <xref:System.Windows.Controls.Menu> contains <xref:System.Windows.Controls.MenuItem> objects that use the <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, and <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> properties and the <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, and <xref:System.Windows.Controls.MenuItem.Click> events.</span></span>  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a><span data-ttu-id="0109c-111">MenuItems con abbreviazioni da tastiera</span><span class="sxs-lookup"><span data-stu-id="0109c-111">MenuItems with Keyboard Shortcuts</span></span>  
 <span data-ttu-id="0109c-112">Tasti di scelta rapida sono combinazioni di caratteri che possono essere immessi con la tastiera per richiamare <xref:System.Windows.Controls.Menu> comandi.</span><span class="sxs-lookup"><span data-stu-id="0109c-112">Keyboard shortcuts are character combinations that can be entered with the keyboard to invoke <xref:System.Windows.Controls.Menu> commands.</span></span> <span data-ttu-id="0109c-113">Il collegamento per **Copia** ad esempio è CTRL+C.</span><span class="sxs-lookup"><span data-stu-id="0109c-113">For example, the shortcut for **Copy** is CTRL+C.</span></span> <span data-ttu-id="0109c-114">Sono disponibili due proprietà da utilizzare con voci di menu e tasti di scelta rapida:<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> o <xref:System.Windows.Controls.MenuItem.Command%2A>.</span><span class="sxs-lookup"><span data-stu-id="0109c-114">There are two properties to use with keyboard shortcuts and menu items —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> or <xref:System.Windows.Controls.MenuItem.Command%2A>.</span></span>  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a><span data-ttu-id="0109c-115">InputGestureText</span><span class="sxs-lookup"><span data-stu-id="0109c-115">InputGestureText</span></span>  
 <span data-ttu-id="0109c-116">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> proprietà a cui assegnare il testo di scelta rapida da tastiera per <xref:System.Windows.Controls.MenuItem> controlli.</span><span class="sxs-lookup"><span data-stu-id="0109c-116">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> property to assign keyboard shortcut text to <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="0109c-117">In questo modo nella voce di menu vengono inserite solo le abbreviazioni da tastiera.</span><span class="sxs-lookup"><span data-stu-id="0109c-117">This only places the keyboard shortcut in the menu item.</span></span>  <span data-ttu-id="0109c-118">Non associare il comando con il <xref:System.Windows.Controls.MenuItem>.</span><span class="sxs-lookup"><span data-stu-id="0109c-118">It does not associate the command with the <xref:System.Windows.Controls.MenuItem>.</span></span> <span data-ttu-id="0109c-119">L'applicazione deve gestire l'input dell'utente per eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="0109c-119">The application must handle the user's input to carry out the action.</span></span>  
  
 [!code-xaml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a><span data-ttu-id="0109c-120">Comando</span><span class="sxs-lookup"><span data-stu-id="0109c-120">Command</span></span>  
 <span data-ttu-id="0109c-121">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.MenuItem.Command%2A> proprietà per associare il **aprire** e **salvare** comandi con <xref:System.Windows.Controls.MenuItem> controlli.</span><span class="sxs-lookup"><span data-stu-id="0109c-121">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.Command%2A> property to associate the **Open** and **Save** commands with <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="0109c-122">La proprietà command non associa solo un comando con un <xref:System.Windows.Controls.MenuItem>, ma fornisce anche il testo di input da utilizzare come un collegamento.</span><span class="sxs-lookup"><span data-stu-id="0109c-122">Not only does the command property associate a command with a <xref:System.Windows.Controls.MenuItem>, but it also supplies the input gesture text to use as a shortcut.</span></span>  
  
 [!code-xaml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <span data-ttu-id="0109c-123">Il <xref:System.Windows.Controls.MenuItem> classe include inoltre un <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> proprietà che specifica l'elemento in cui si verifica il comando.</span><span class="sxs-lookup"><span data-stu-id="0109c-123">The <xref:System.Windows.Controls.MenuItem> class also has a <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> property, which specifies the element where the command occurs.</span></span> <span data-ttu-id="0109c-124">Se <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> non è impostata, l'elemento con stato attivo della tastiera riceve il comando.</span><span class="sxs-lookup"><span data-stu-id="0109c-124">If <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> is not set, the element that has keyboard focus receives the command.</span></span> <span data-ttu-id="0109c-125">Per altre informazioni sui comandi vedere [Cenni preliminari sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0109c-125">For more information about commands, see [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a><span data-ttu-id="0109c-126">Applicazione di stili al testo</span><span class="sxs-lookup"><span data-stu-id="0109c-126">Menu Styling</span></span>  
 <span data-ttu-id="0109c-127">Con lo stile di controllo, è possibile modificare drasticamente l'aspetto e il comportamento di <xref:System.Windows.Controls.Menu> controlli senza dover scrivere un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0109c-127">With control styling, you can dramatically change the appearance and behavior of <xref:System.Windows.Controls.Menu> controls without having to write a custom control.</span></span> <span data-ttu-id="0109c-128">Oltre a impostare la proprietà visive, è inoltre possibile applicare un <xref:System.Windows.Style> a singole parti di un controllo, il comportamento di parti del controllo tramite le proprietà, modificare o aggiungere parti aggiuntive o modificare il layout di un controllo.</span><span class="sxs-lookup"><span data-stu-id="0109c-128">In addition to setting visual properties, you can also apply a <xref:System.Windows.Style> to individual parts of a control, change the behavior of parts of the control through properties, or add additional parts or change the layout of a control.</span></span> <span data-ttu-id="0109c-129">Gli esempi seguenti illustrano diversi modi per aggiungere un <xref:System.Windows.Style> per un <xref:System.Windows.Controls.Menu> controllo.</span><span class="sxs-lookup"><span data-stu-id="0109c-129">The following examples demonstrate several ways to add a <xref:System.Windows.Style> to a <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 <span data-ttu-id="0109c-130">Nel primo esempio di codice definisce un <xref:System.Windows.Style> chiamato `Simple` che viene illustrato come utilizzare le impostazioni di sistema correnti nello stile.</span><span class="sxs-lookup"><span data-stu-id="0109c-130">The first code example defines a <xref:System.Windows.Style> called `Simple` that shows how to use the current system settings in your style.</span></span> <span data-ttu-id="0109c-131">Il codice assegna il colore di `MenuHighlightBrush` come colore di sfondo del menu e `MenuTextBrush` come colore di primo piano del menu.</span><span class="sxs-lookup"><span data-stu-id="0109c-131">The code assigns the color of the `MenuHighlightBrush` as the menu's background color and the `MenuTextBrush` as the menu's foreground color.</span></span> <span data-ttu-id="0109c-132">Si noti l'uso delle chiavi di risorsa per assegnare i pennelli.</span><span class="sxs-lookup"><span data-stu-id="0109c-132">Notice that you use resource keys to assign the brushes.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 <span data-ttu-id="0109c-133">L'esempio seguente usa <xref:System.Windows.Trigger> gli elementi che consentono di modificare l'aspetto di un <xref:System.Windows.Controls.MenuItem> in risposta a eventi che si verificano nel <xref:System.Windows.Controls.Menu>.</span><span class="sxs-lookup"><span data-stu-id="0109c-133">The following sample uses <xref:System.Windows.Trigger> elements that enable you to change the appearance of a <xref:System.Windows.Controls.MenuItem> in response to events that occur on the <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="0109c-134">Quando si sposta il puntatore del mouse su di <xref:System.Windows.Controls.Menu>, il colore primo piano e le caratteristiche del carattere delle voci di menu Modifica.</span><span class="sxs-lookup"><span data-stu-id="0109c-134">When you move the mouse over the <xref:System.Windows.Controls.Menu>, the foreground color and the font characteristics of the menu items change.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0109c-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0109c-135">See Also</span></span>  
 [<span data-ttu-id="0109c-136">Esempio di raccolta di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="0109c-136">WPF Controls Gallery Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160053)
