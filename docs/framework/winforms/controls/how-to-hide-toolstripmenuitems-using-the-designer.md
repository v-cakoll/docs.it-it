---
title: 'Procedura: nascondere ToolStripMenuItems utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9549fa11b3f019dce3cc77d5f6d1d08a8485f0cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="393d5-102">Procedura: nascondere ToolStripMenuItems utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="393d5-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="393d5-103">Nascondere le voci di menu è un modo per controllare l'interfaccia utente (UI) dell'applicazione e limitare i comandi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="393d5-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="393d5-104">Spesso, è possibile nascondere un intero menu quando tutte le voci di menu su di esso non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="393d5-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="393d5-105">Distrazioni per l'utente.</span><span class="sxs-lookup"><span data-stu-id="393d5-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="393d5-106">Inoltre, potrebbe essere da nascondere e disabilitare il menu o una voce di menu come nasconderlo solamente non impedire all'utente l'accesso a un comando di menu con un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="393d5-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="393d5-107">Per ulteriori informazioni sulla disabilitazione di voci di menu, vedere [procedura: disabilitare ToolStripMenuItems usando la finestra di progettazione](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="393d5-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="393d5-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="393d5-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="393d5-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="393d5-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="393d5-110">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="393d5-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="393d5-111">Per nascondere un menu di primo livello e delle relative voci di sottomenu</span><span class="sxs-lookup"><span data-stu-id="393d5-111">To hide a top-level menu and its submenu items</span></span>  
  
1.  <span data-ttu-id="393d5-112">Selezionare la voce di menu di primo livello e impostare il relativo <xref:System.Windows.Forms.ToolStripItem.Visible%2A> o <xref:System.Windows.Forms.ToolStripItem.Available%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="393d5-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="393d5-113">Quando si nasconde la voce di menu di primo livello, sono nascoste anche tutte le voci di menu all'interno di tale menu.</span><span class="sxs-lookup"><span data-stu-id="393d5-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="393d5-114">Se si fa clic in una posizione diversa sul <xref:System.Windows.Forms.MenuStrip> dopo l'impostazione <xref:System.Windows.Forms.ToolStripItem.Visible%2A> a `false`, la voce di menu di primo livello intero e relative voci di sottomenu vengono rimosse dal form, così che mostra l'effetto in fase di esecuzione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="393d5-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="393d5-115">Per visualizzare la voce di menu di primo livello in fase di progettazione, fare clic su di <xref:System.Windows.Forms.MenuStrip> nel **sulla barra dei componenti**nella **struttura documento**, o nella parte superiore della griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="393d5-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="393d5-116">Raramente sarà necessario nascondere un intero menu ad eccezione di più i menu figlio MDI (interfaccia) documento in uno scenario di unione.</span><span class="sxs-lookup"><span data-stu-id="393d5-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="393d5-117">Per nascondere una voce di sottomenu</span><span class="sxs-lookup"><span data-stu-id="393d5-117">To hide a submenu item</span></span>  
  
1.  <span data-ttu-id="393d5-118">Selezionare la voce di sottomenu e impostare il relativo <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="393d5-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="393d5-119">Quando si nasconde una voce di sottomenu, rimane visibile sul form in fase di progettazione in modo che è possibile selezionare con facilità per ulteriore lavoro.</span><span class="sxs-lookup"><span data-stu-id="393d5-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="393d5-120">Verranno effettivamente nascoste in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="393d5-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="393d5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="393d5-121">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [<span data-ttu-id="393d5-122">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="393d5-122">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="393d5-123">Procedura: Disabilitare i ToolStripMenuItems con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="393d5-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
