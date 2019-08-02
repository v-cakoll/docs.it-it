---
title: Cenni preliminari sul controllo MenuStrip (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 46a3a25415db77ee261f5fb1c3bf114b2275a2d4
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733450"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="72185-102">Cenni preliminari sul controllo MenuStrip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="72185-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="72185-103">I menu espongono le funzionalità agli utenti con i comandi raggruppati in base a un tema comune.</span><span class="sxs-lookup"><span data-stu-id="72185-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="72185-104">Il <xref:System.Windows.Forms.MenuStrip> controllo è stato introdotto nella versione 2,0 del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72185-104">The <xref:System.Windows.Forms.MenuStrip> control was introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="72185-105">Con il <xref:System.Windows.Forms.MenuStrip> controllo è possibile creare facilmente menu come quelli disponibili in Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="72185-105">With the <xref:System.Windows.Forms.MenuStrip> control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="72185-106">Il <xref:System.Windows.Forms.MenuStrip> controllo supporta l'interfaccia a documenti multipli (MDI) e l'Unione di menu, le descrizioni comandi e l'overflow.</span><span class="sxs-lookup"><span data-stu-id="72185-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="72185-107">È possibile migliorare l'usabilità e la leggibilità dei menu aggiungendo chiavi di accesso, tasti di scelta rapida, segni di spunta, immagini e barre dei separatori.</span><span class="sxs-lookup"><span data-stu-id="72185-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="72185-108">Il <xref:System.Windows.Forms.MenuStrip> controllo sostituisce e aggiunge funzionalità <xref:System.Windows.Forms.MainMenu> al controllo; tuttavia, il <xref:System.Windows.Forms.MainMenu> controllo viene mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se lo si sceglie.</span><span class="sxs-lookup"><span data-stu-id="72185-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="72185-109">Modalità di utilizzo del controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="72185-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="72185-110">Usare il <xref:System.Windows.Forms.MenuStrip> controllo per:</span><span class="sxs-lookup"><span data-stu-id="72185-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
- <span data-ttu-id="72185-111">Consente di creare menu facilmente personalizzati e di uso comune che supportano funzionalità avanzate di interfaccia utente e layout, ad esempio ordinamento e allineamento di testo e immagini, operazioni di trascinamento della selezione, MDI, overflow e modalità alternative di accesso ai comandi di menu.</span><span class="sxs-lookup"><span data-stu-id="72185-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
- <span data-ttu-id="72185-112">Supportare l'aspetto e il comportamento tipici del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="72185-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
- <span data-ttu-id="72185-113">Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo in cui si gestiscono gli eventi per altri controlli.</span><span class="sxs-lookup"><span data-stu-id="72185-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="72185-114">Nella tabella seguente vengono illustrate alcune proprietà particolarmente <xref:System.Windows.Forms.MenuStrip> importanti di e delle classi associate.</span><span class="sxs-lookup"><span data-stu-id="72185-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="72185-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="72185-115">Property</span></span>|<span data-ttu-id="72185-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="72185-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="72185-117">Ottiene o imposta l' <xref:System.Windows.Forms.ToolStripMenuItem> oggetto utilizzato per visualizzare un elenco di form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="72185-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="72185-118">Ottiene o imposta il modo in cui i menu figlio vengono uniti ai menu padre nelle applicazioni MDI.</span><span class="sxs-lookup"><span data-stu-id="72185-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="72185-119">Ottiene o imposta la posizione di un elemento unito all'interno di un menu in applicazioni MDI.</span><span class="sxs-lookup"><span data-stu-id="72185-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="72185-120">Ottiene o imposta un valore che indica se il form è un contenitore per form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="72185-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="72185-121">Ottiene o imposta un valore che indica se vengono visualizzate le <xref:System.Windows.Forms.MenuStrip>descrizioni comandi per.</span><span class="sxs-lookup"><span data-stu-id="72185-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="72185-122">Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.MenuStrip> supporta la funzionalità di overflow.</span><span class="sxs-lookup"><span data-stu-id="72185-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="72185-123">Ottiene o imposta i tasti di scelta rapida associati <xref:System.Windows.Forms.ToolStripMenuItem>a.</span><span class="sxs-lookup"><span data-stu-id="72185-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="72185-124">Ottiene o imposta un valore che indica se i tasti di scelta rapida associati a <xref:System.Windows.Forms.ToolStripMenuItem> sono visualizzati accanto <xref:System.Windows.Forms.ToolStripMenuItem>a.</span><span class="sxs-lookup"><span data-stu-id="72185-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="72185-125">Nella tabella seguente vengono illustrate <xref:System.Windows.Forms.MenuStrip> le principali classi complementari.</span><span class="sxs-lookup"><span data-stu-id="72185-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="72185-126">Classe</span><span class="sxs-lookup"><span data-stu-id="72185-126">Class</span></span>|<span data-ttu-id="72185-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72185-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="72185-128">Rappresenta un'opzione selezionabile visualizzata in un <xref:System.Windows.Forms.MenuStrip> oggetto <xref:System.Windows.Forms.ContextMenuStrip>o.</span><span class="sxs-lookup"><span data-stu-id="72185-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="72185-129">Viene visualizzato un menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="72185-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="72185-130">Rappresenta un controllo che consente all'utente di selezionare un singolo elemento da un elenco visualizzato quando l'utente fa clic su <xref:System.Windows.Forms.ToolStripDropDownButton> o su una voce di menu di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="72185-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="72185-131">Fornisce la funzionalità di base per i <xref:System.Windows.Forms.ToolStripItem> controlli derivati da che visualizzano gli elementi a discesa quando vengono selezionate.</span><span class="sxs-lookup"><span data-stu-id="72185-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72185-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72185-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
