---
title: 'Procedura: Aggiungere e rimuovere voci di menu con il componente ContextMenu di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: cf70a5cc426b6c6075d1deb11aa2685c39a065c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640335"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="9ee61-102">Procedura: Aggiungere e rimuovere voci di menu con il componente ContextMenu di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ee61-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="9ee61-103">Viene illustrato come aggiungere e rimuovere voci di menu di scelta rapida in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="9ee61-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="9ee61-104">I moduli di Windows <xref:System.Windows.Forms.ContextMenu> componente fornisce un menu dei comandi usati frequentemente rilevanti per l'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="9ee61-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="9ee61-105">È possibile aggiungere elementi al menu di scelta rapida aggiungendo <xref:System.Windows.Forms.MenuItem> gli oggetti per il <xref:System.Windows.Forms.Menu.MenuItems%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="9ee61-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="9ee61-106">È possibile rimuovere elementi da un menu di scelta rapida in modo permanente; in fase di esecuzione, tuttavia, potrebbe essere più appropriato nascondere o disabilitare le voci.</span><span class="sxs-lookup"><span data-stu-id="9ee61-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ee61-107">Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere la funzionalità per il <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="9ee61-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="9ee61-108">Per rimuovere gli elementi da un menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="9ee61-108">To remove items from a shortcut menu</span></span>  
  
1. <span data-ttu-id="9ee61-109">Usare la <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> o <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> metodo del <xref:System.Windows.Forms.Menu.MenuItems%2A> insieme del <xref:System.Windows.Forms.ContextMenu> componente per rimuovere una voce di menu specifico.</span><span class="sxs-lookup"><span data-stu-id="9ee61-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     <span data-ttu-id="9ee61-110">-oppure-</span><span class="sxs-lookup"><span data-stu-id="9ee61-110">-or-</span></span>  
  
2. <span data-ttu-id="9ee61-111">Usare la `Clear` metodo del `MenuItems` insieme del <xref:System.Windows.Forms.ContextMenu> componenti da rimuovere tutti gli elementi nel menu.</span><span class="sxs-lookup"><span data-stu-id="9ee61-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9ee61-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ee61-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="9ee61-113">Componente ContextMenu</span><span class="sxs-lookup"><span data-stu-id="9ee61-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="9ee61-114">Panoramica sul componente ContextMenu</span><span class="sxs-lookup"><span data-stu-id="9ee61-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
