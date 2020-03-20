---
title: Cenni preliminari sull'oggetto ContextMenu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: 4d2d8db0f614b5240705146dbe91432b96b46dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185907"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="2c318-102">Cenni preliminari sull'oggetto ContextMenu</span><span class="sxs-lookup"><span data-stu-id="2c318-102">ContextMenu Overview</span></span>
<span data-ttu-id="2c318-103">La <xref:System.Windows.Controls.ContextMenu> classe rappresenta l'elemento che espone funzionalità <xref:System.Windows.Controls.Menu>utilizzando un oggetto specifico del contesto.</span><span class="sxs-lookup"><span data-stu-id="2c318-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="2c318-104">In genere, un <xref:System.Windows.Controls.ContextMenu> utente [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] espone l'oggetto in facendo clic con il pulsante destro del mouse sul pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="2c318-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="2c318-105">In questo argomento <xref:System.Windows.Controls.ContextMenu> viene presentato l'elemento e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] vengono forniti esempi di come utilizzarlo in e nel codice.</span><span class="sxs-lookup"><span data-stu-id="2c318-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a><span data-ttu-id="2c318-106">Controllo ContextMenu</span><span class="sxs-lookup"><span data-stu-id="2c318-106">ContextMenu Control</span></span>  
 <span data-ttu-id="2c318-107">A <xref:System.Windows.Controls.ContextMenu> è collegato a un controllo specifico.</span><span class="sxs-lookup"><span data-stu-id="2c318-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="2c318-108">L'elemento <xref:System.Windows.Controls.ContextMenu> consente di presentare agli utenti un elenco di elementi che specificano comandi <xref:System.Windows.Controls.Button>o opzioni associati a un determinato controllo, ad esempio un oggetto .</span><span class="sxs-lookup"><span data-stu-id="2c318-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="2c318-109">Gli utenti possono fare clic con il pulsante destro del mouse sul controllo per visualizzare il menu.</span><span class="sxs-lookup"><span data-stu-id="2c318-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="2c318-110">In genere, <xref:System.Windows.Controls.MenuItem> facendo clic su un apre un sottomenu o viene emesso un comando da parte di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c318-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a><span data-ttu-id="2c318-111">Creazione di elementi ContextMenu</span><span class="sxs-lookup"><span data-stu-id="2c318-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="2c318-112">Negli esempi seguenti viene <xref:System.Windows.Controls.ContextMenu> illustrato come creare un con sottomenu.</span><span class="sxs-lookup"><span data-stu-id="2c318-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="2c318-113">I <xref:System.Windows.Controls.ContextMenu> controlli sono associati ai controlli pulsante.</span><span class="sxs-lookup"><span data-stu-id="2c318-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="2c318-114">Applicazione di stili a un elemento ContextMenu</span><span class="sxs-lookup"><span data-stu-id="2c318-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="2c318-115">Utilizzando un <xref:System.Windows.Style>controllo , è possibile modificare notevolmente l'aspetto e il comportamento di un <xref:System.Windows.Controls.ContextMenu> senza scrivere un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2c318-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="2c318-116">Oltre a impostare proprietà visive, è anche possibile applicare stili alle parti di un controllo.</span><span class="sxs-lookup"><span data-stu-id="2c318-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="2c318-117">Ad esempio, è possibile modificare il comportamento di parti del controllo utilizzando le proprietà oppure <xref:System.Windows.Controls.ContextMenu>aggiungere parti o modificare il layout di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="2c318-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="2c318-118">Negli esempi seguenti vengono illustrati <xref:System.Windows.Controls.ContextMenu> diversi modi per aggiungere stili ai controlli.</span><span class="sxs-lookup"><span data-stu-id="2c318-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="2c318-119">Nel primo esempio viene definito uno stile denominato `SimpleSysResources`, che illustra come usare le impostazioni di sistema correnti nello stile.</span><span class="sxs-lookup"><span data-stu-id="2c318-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="2c318-120">L'esempio <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> viene <xref:System.Windows.Controls.Control.Background%2A> assegnato <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> come <xref:System.Windows.Controls.Control.Foreground%2A> colore e <xref:System.Windows.Controls.ContextMenu>come colore dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="2c318-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="2c318-121">Nell'esempio riportato di seguito viene utilizzato l'elemento <xref:System.Windows.Trigger> per modificare l'aspetto di un <xref:System.Windows.Controls.Menu> oggetto in risposta agli eventi generati nell'oggetto <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="2c318-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="2c318-122">Quando un utente sposta il mouse sul <xref:System.Windows.Controls.ContextMenu> menu, l'aspetto degli elementi cambia.</span><span class="sxs-lookup"><span data-stu-id="2c318-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c318-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c318-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="2c318-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="2c318-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="2c318-125">Stili e modelli di ContextMenu</span><span class="sxs-lookup"><span data-stu-id="2c318-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- [<span data-ttu-id="2c318-126">Esempio di raccolta di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="2c318-126">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
