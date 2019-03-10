---
title: 'Procedura: Aggiungere e rimuovere voci di Menu con il componente ContextMenu di Windows Form'
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
ms.openlocfilehash: 8b63182bdb37e47a71bee2d22500263cd4889ac9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725064"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>Procedura: Aggiungere e rimuovere voci di Menu con il componente ContextMenu di Windows Form
Viene illustrato come aggiungere e rimuovere voci di menu di scelta rapida in Windows Form.  
  
 I moduli di Windows <xref:System.Windows.Forms.ContextMenu> componente fornisce un menu dei comandi usati frequentemente rilevanti per l'oggetto selezionato. È possibile aggiungere elementi al menu di scelta rapida aggiungendo <xref:System.Windows.Forms.MenuItem> gli oggetti per il <xref:System.Windows.Forms.Menu.MenuItems%2A> raccolta.  
  
 È possibile rimuovere elementi da un menu di scelta rapida in modo permanente; in fase di esecuzione, tuttavia, potrebbe essere più appropriato nascondere o disabilitare le voci.  
  
> [!IMPORTANT]
>  Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere la funzionalità per il <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si sceglie.  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>Per rimuovere gli elementi da un menu di scelta rapida  
  
1.  Usare la <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> o <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> metodo del <xref:System.Windows.Forms.Menu.MenuItems%2A> insieme del <xref:System.Windows.Forms.ContextMenu> componente per rimuovere una voce di menu specifico.  
  
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
  
     -oppure-  
  
2.  Usare la `Clear` metodo del `MenuItems` insieme del <xref:System.Windows.Forms.ContextMenu> componenti da rimuovere tutti gli elementi nel menu.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ContextMenu>
- [Componente ContextMenu](contextmenu-component-windows-forms.md)
- [Panoramica sul componente ContextMenu](contextmenu-component-overview-windows-forms.md)
