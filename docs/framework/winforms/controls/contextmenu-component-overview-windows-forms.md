---
title: Cenni preliminari sul componente ContextMenu (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 5d548815533e8f9bb37ad00129a5ae526612ea08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526123"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="9e391-102">Cenni preliminari sul componente ContextMenu (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="9e391-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="9e391-103">Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e un utilizzo futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="9e391-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="9e391-104">Windows Form <xref:System.Windows.Forms.ContextMenu> componente, è possibile fornire agli utenti con un menu di scelta rapida facilmente accessibile di comandi utilizzati frequentemente vengono associati all'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="9e391-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="9e391-105">Gli elementi in un menu di scelta rapida sono spesso un sottoinsieme degli elementi dei menu principali vengono visualizzati in un' posizione nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9e391-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="9e391-106">Un utente di accedere in genere un menu di scelta rapida facendo clic con il mouse.</span><span class="sxs-lookup"><span data-stu-id="9e391-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="9e391-107">In Windows Form, vengono associati ai controlli menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9e391-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="9e391-108">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="9e391-108">Key Properties</span></span>  
 <span data-ttu-id="9e391-109">È possibile associare un menu di scelta rapida con un controllo mediante l'impostazione del controllo <xref:System.Windows.Forms.Control.ContextMenu%2A> proprietà per il <xref:System.Windows.Forms.ContextMenu> componente.</span><span class="sxs-lookup"><span data-stu-id="9e391-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="9e391-110">Menu di scelta rapida singolo può essere associato a più controlli, ma ciascuno può essere solo un menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9e391-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="9e391-111">La proprietà chiave di <xref:System.Windows.Forms.ContextMenu> componente è il <xref:System.Windows.Forms.Menu.MenuItems%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e391-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="9e391-112">È possibile aggiungere voci di menu a livello di programmazione creando <xref:System.Windows.Forms.MenuItem> oggetti e aggiungendoli al <xref:System.Windows.Forms.Menu.MenuItemCollection> del menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9e391-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="9e391-113">Poiché gli elementi in un menu di scelta rapida sono in genere creati da altri menu, è più di frequente verranno aggiungere elementi a un menu di scelta rapida copiandoli.</span><span class="sxs-lookup"><span data-stu-id="9e391-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e391-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e391-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenu>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>
