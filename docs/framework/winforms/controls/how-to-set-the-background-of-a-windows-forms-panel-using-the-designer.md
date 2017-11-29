---
title: 'Procedura: impostare lo sfondo di un controllo Panel Windows Form mediante la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 56cb6f7ee9a7c52ff4763c0c310d679e4889dbd2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="3e755-102">Procedura: impostare lo sfondo di un controllo Panel Windows Form mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3e755-102">How to: Set the Background of a Windows Forms Panel Using the Designer</span></span>
<span data-ttu-id="3e755-103">Un Windows Form <xref:System.Windows.Forms.Panel> controllo può visualizzare un colore di sfondo sia un'immagine di sfondo.</span><span class="sxs-lookup"><span data-stu-id="3e755-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="3e755-104">Il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà imposta il colore di sfondo per i controlli contenuti nel pannello, ad esempio le etichette e pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="3e755-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="3e755-105">Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, il <xref:System.Windows.Forms.Control.BackColor%2A> tutto il pannello verrà riempito dalla selezione.</span><span class="sxs-lookup"><span data-stu-id="3e755-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="3e755-106">Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, verrà visualizzata l'immagine dietro i controlli contenuti nel pannello.</span><span class="sxs-lookup"><span data-stu-id="3e755-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>  
  
 <span data-ttu-id="3e755-107">La procedura seguente richiede un **applicazione Windows** progetto con un modulo che contiene un <xref:System.Windows.Forms.Panel> controllo.</span><span class="sxs-lookup"><span data-stu-id="3e755-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="3e755-108">Per informazioni su come configurare questo tipo di progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3e755-108">For information about how to set up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e755-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="3e755-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3e755-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="3e755-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3e755-111">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="3e755-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="3e755-112">Per impostare lo sfondo in Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="3e755-112">To set the background in the Windows Forms Designer</span></span>  
  
1.  <span data-ttu-id="3e755-113">Selezionare il controllo <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="3e755-113">Select the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
2.  <span data-ttu-id="3e755-114">Nel **proprietà** finestra fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackColor%2A> proprietà per visualizzare una finestra con tre schede.</span><span class="sxs-lookup"><span data-stu-id="3e755-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>  
  
3.  <span data-ttu-id="3e755-115">Selezionare il **personalizzato** scheda per visualizzare una tavolozza di colori.</span><span class="sxs-lookup"><span data-stu-id="3e755-115">Select the **Custom** tab to display a palette of colors.</span></span>  
  
4.  <span data-ttu-id="3e755-116">Selezionare il **Web** o **sistema** scheda per visualizzare un elenco di nomi predefiniti dei colori e quindi selezionare un colore.</span><span class="sxs-lookup"><span data-stu-id="3e755-116">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>  
  
5.  <span data-ttu-id="3e755-117">Nel **proprietà** finestra fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3e755-117">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>  
  
6.  <span data-ttu-id="3e755-118">Nel **aprire** finestra di dialogo, selezionare il file che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="3e755-118">In the **Open** dialog box, select the file that you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e755-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e755-119">See Also</span></span>  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [<span data-ttu-id="3e755-120">Controllo Panel</span><span class="sxs-lookup"><span data-stu-id="3e755-120">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="3e755-121">Panoramica sul controllo Panel</span><span class="sxs-lookup"><span data-stu-id="3e755-121">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="3e755-122">Procedura: Raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3e755-122">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
