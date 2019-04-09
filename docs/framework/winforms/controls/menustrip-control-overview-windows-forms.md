---
title: Cenni preliminari sul controllo MenuStrip (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 7cd761697a09205294727043efc6cf73816803ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144352"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="01e47-102">Cenni preliminari sul controllo MenuStrip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="01e47-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="01e47-103">I menu che contiene i comandi che vengono raggruppati in base a un tema comune espongono funzionalità agli utenti.</span><span class="sxs-lookup"><span data-stu-id="01e47-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="01e47-104">Il <xref:System.Windows.Forms.MenuStrip> controllo è una novità di questa versione di Visual Studio e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01e47-104">The <xref:System.Windows.Forms.MenuStrip> control is new to this version of Visual Studio and the .NET Framework.</span></span> <span data-ttu-id="01e47-105">Con il controllo, è possibile creare con facilità i menu, ad esempio quelle disponibili in Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="01e47-105">With the control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="01e47-106">Il <xref:System.Windows.Forms.MenuStrip> controllo supporta l'interfaccia a documenti multipli (MDI) e unione di menu, le descrizioni comandi e overflow.</span><span class="sxs-lookup"><span data-stu-id="01e47-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="01e47-107">È possibile migliorare l'usabilità e migliorare la leggibilità dei menu tramite l'aggiunta di chiavi di accesso, tasti di scelta rapida, segni di spunta, immagini e le barre di separazione.</span><span class="sxs-lookup"><span data-stu-id="01e47-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="01e47-108">Il <xref:System.Windows.Forms.MenuStrip> sostituisce e aggiunge funzionalità per il <xref:System.Windows.Forms.MainMenu> controllare; tuttavia, il <xref:System.Windows.Forms.MainMenu> controllo è stato mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se necessario.</span><span class="sxs-lookup"><span data-stu-id="01e47-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="01e47-109">Modi per usare il controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="01e47-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="01e47-110">Usare il <xref:System.Windows.Forms.MenuStrip> controllo:</span><span class="sxs-lookup"><span data-stu-id="01e47-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
-   <span data-ttu-id="01e47-111">Creare con facilità personalizzato, impiego frequente menu che supportano funzionalità avanzate di utente interfaccia e il layout, come testo e immagine di ordinamento e l'allineamento, operazioni di trascinamento e rilascio, MDI, overflow e modalità alternative di accedere ai comandi di menu.</span><span class="sxs-lookup"><span data-stu-id="01e47-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
-   <span data-ttu-id="01e47-112">Supporta l'aspetto tipico e il comportamento del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="01e47-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
-   <span data-ttu-id="01e47-113">Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo è possibile gestire gli eventi per altri controlli.</span><span class="sxs-lookup"><span data-stu-id="01e47-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="01e47-114">Nella tabella seguente mostra alcune proprietà particolarmente importante di <xref:System.Windows.Forms.MenuStrip> e classi associate.</span><span class="sxs-lookup"><span data-stu-id="01e47-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="01e47-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="01e47-115">Property</span></span>|<span data-ttu-id="01e47-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01e47-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="01e47-117">Ottiene o imposta il <xref:System.Windows.Forms.ToolStripMenuItem> che consente di visualizzare un elenco di form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="01e47-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="01e47-118">Ottiene o imposta il modo in cui i menu figlio vengono uniti ai menu padre nelle applicazioni MDI.</span><span class="sxs-lookup"><span data-stu-id="01e47-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="01e47-119">Ottiene o imposta la posizione di un elemento unito all'interno di un menu nelle applicazioni MDI.</span><span class="sxs-lookup"><span data-stu-id="01e47-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="01e47-120">Ottiene o imposta un valore che indica se il form è un contenitore per form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="01e47-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="01e47-121">Ottiene o imposta un valore che indica se le descrizioni comandi vengono visualizzate per il <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="01e47-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="01e47-122">Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.MenuStrip> supporta la funzionalità di overflow.</span><span class="sxs-lookup"><span data-stu-id="01e47-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="01e47-123">Ottiene o imposta i tasti di scelta rapida associati il <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="01e47-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="01e47-124">Ottiene o imposta un valore che indica se i tasti di scelta rapida sono associati i <xref:System.Windows.Forms.ToolStripMenuItem> sono visualizzati accanto al <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="01e47-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="01e47-125">La tabella seguente illustra l'importante <xref:System.Windows.Forms.MenuStrip> classi correlate.</span><span class="sxs-lookup"><span data-stu-id="01e47-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="01e47-126">Classe</span><span class="sxs-lookup"><span data-stu-id="01e47-126">Class</span></span>|<span data-ttu-id="01e47-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01e47-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="01e47-128">Rappresenta un'opzione selezionabile visualizzata in una <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="01e47-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="01e47-129">Viene visualizzato un menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="01e47-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="01e47-130">Rappresenta un controllo che consente all'utente di selezionare un singolo elemento da un elenco che viene visualizzato quando l'utente sceglie un <xref:System.Windows.Forms.ToolStripDropDownButton> o una voce di menu di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="01e47-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="01e47-131">Fornisce funzionalità di base per i controlli derivano da <xref:System.Windows.Forms.ToolStripItem> che visualizzano gli elementi di elenco a discesa quando si fa clic.</span><span class="sxs-lookup"><span data-stu-id="01e47-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01e47-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01e47-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
