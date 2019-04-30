---
title: 'Procedura: Nascondere ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: dc9daa945f2a546548f2cc6ea033378bd9ceff93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941222"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="a483e-102">Procedura: Nascondere ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="a483e-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="a483e-103">Se si nasconde le voci di menu è un modo per controllare l'interfaccia utente dell'applicazione e limitare i comandi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a483e-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="a483e-104">Spesso, è consigliabile nascondere un intero menu quando tutte le voci di menu su di esso non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="a483e-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="a483e-105">Evitare distrazioni per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a483e-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="a483e-106">Inoltre, si potrebbe voler nascondere e disabilitare il menu o la voce di menu, come nascondere da solo non impedisce all'utente di accesso a un comando di menu tramite un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a483e-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="a483e-107">Per nascondere qualsiasi voce di menu a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a483e-107">To hide any menu item programmatically</span></span>  
  
- <span data-ttu-id="a483e-108">All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere il codice per impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="a483e-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a483e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a483e-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="a483e-110">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="a483e-110">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="a483e-111">Procedura: Disabilitare i ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="a483e-111">How to: Disable ToolStripMenuItems</span></span>](how-to-disable-toolstripmenuitems.md)
