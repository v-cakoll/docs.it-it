---
title: 'Procedura: aggiungere e rimuovere schede con il controllo TabControl Windows Form mediante la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e603e420be2c5be6174fab3876008fdf73c8459
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="3990c-102">Procedura: aggiungere e rimuovere schede con il controllo TabControl Windows Form mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3990c-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="3990c-103">Quando si inserisce un <xref:System.Windows.Forms.TabControl> controllo sul form, contiene due schede per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3990c-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="3990c-104">È possibile aggiungere o rimuovere schede, utilizzando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3990c-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="3990c-105">La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.TabControl> controllo.</span><span class="sxs-lookup"><span data-stu-id="3990c-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="3990c-106">Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3990c-106">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3990c-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="3990c-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3990c-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="3990c-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3990c-109">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="3990c-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="3990c-110">Per aggiungere o rimuovere una scheda usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3990c-110">To add or remove a tab using the designer</span></span>  
  
-   <span data-ttu-id="3990c-111">Nello smart tag del controllo, fare clic su **Aggiungi scheda** o **Rimuovi scheda**</span><span class="sxs-lookup"><span data-stu-id="3990c-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="3990c-112">oppure</span><span class="sxs-lookup"><span data-stu-id="3990c-112">-or-</span></span>  
  
     <span data-ttu-id="3990c-113">Nel **proprietà** finestra, fare clic su di **i puntini di sospensione** pulsante (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto a il <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà per aprire la **Editor della raccolta TabPage**.</span><span class="sxs-lookup"><span data-stu-id="3990c-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="3990c-114">Fare clic su di **Aggiungi** o **rimuovere** pulsante.</span><span class="sxs-lookup"><span data-stu-id="3990c-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3990c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3990c-115">See Also</span></span>  
 [<span data-ttu-id="3990c-116">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="3990c-116">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="3990c-117">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="3990c-117">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="3990c-118">Procedura: Aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="3990c-118">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="3990c-119">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="3990c-119">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="3990c-120">Procedura: Modificare l'aspetto del controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3990c-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
