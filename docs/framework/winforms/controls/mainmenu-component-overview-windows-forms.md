---
title: Cenni preliminari sul componente MainMenu (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: da1b76a7019f364e7463a8345aa80d9a9bd6089e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168480"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="53d40-102">Cenni preliminari sul componente MainMenu (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="53d40-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="53d40-103">Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere la funzionalità per il <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="53d40-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="53d40-104">I moduli di Windows <xref:System.Windows.Forms.MainMenu> componente consente di visualizzare un menu di scelta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="53d40-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="53d40-105">Tutti i sottomenu del menu principale e singoli elementi sono <xref:System.Windows.Forms.MenuItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="53d40-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="53d40-106">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="53d40-106">Key Properties</span></span>  
 <span data-ttu-id="53d40-107">Una voce di menu può essere designata come elemento predefinito impostando la <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="53d40-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="53d40-108">L'elemento predefinito viene visualizzato in grassetto quando si fa clic sul menu.</span><span class="sxs-lookup"><span data-stu-id="53d40-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="53d40-109">La voce di menu <xref:System.Windows.Forms.MenuItem.Checked%2A> la proprietà `true` o `false`e indica se la voce di menu è selezionata.</span><span class="sxs-lookup"><span data-stu-id="53d40-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="53d40-110">La voce di menu <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> proprietà consente di personalizzare l'aspetto dell'elemento selezionato: se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostata su `true`, un pulsante di opzione viene visualizzata accanto all'elemento; se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `false`, viene visualizzato un segno di spunta accanto all'elemento.</span><span class="sxs-lookup"><span data-stu-id="53d40-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d40-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53d40-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="53d40-112">Panoramica del controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="53d40-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
