---
title: 'Procedura: raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1d4a49f36ac294199871075a04b7e682bd5613b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="bc5f5-102">Procedura: raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="bc5f5-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="bc5f5-103">Windows Form <xref:System.Windows.Forms.Panel> controlli vengono utilizzati per raggruppare altri controlli.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="bc5f5-104">Vi sono tre motivi per i controlli di gruppo.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-104">There are three reasons to group controls.</span></span> <span data-ttu-id="bc5f5-105">Raggruppamento di elementi di form per un'interfaccia utente deselezionare; visivo un vantaggio è a livello di codice raggruppamento di pulsanti di opzione, ad esempio; l'ultimo si per spostare i controlli in un'unità in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc5f5-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bc5f5-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="bc5f5-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bc5f5-108">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="bc5f5-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="bc5f5-109">Per creare un gruppo di controlli</span><span class="sxs-lookup"><span data-stu-id="bc5f5-109">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="bc5f5-110">Trascinare un <xref:System.Windows.Forms.Panel> controllo il **Windows Form** della casella degli strumenti in un form.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2.  <span data-ttu-id="bc5f5-111">Aggiungere altri controlli al pannello, creando ciascun all'interno del pannello.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="bc5f5-112">Se si dispone di controlli esistenti che si desidera inserire in un pannello, è possibile selezionare tutti i controlli, li tagliare negli Appunti, selezionare il <xref:System.Windows.Forms.Panel> controllare e incollarli quindi nel pannello.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="bc5f5-113">È anche possibile trascinare i controlli nel pannello.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-113">You can also drag them into the panel.</span></span>  
  
3.  <span data-ttu-id="bc5f5-114">(Facoltativo) Se si desidera aggiungere un bordo a un pannello, impostare il relativo <xref:System.Windows.Forms.BorderStyle> proprietà.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="bc5f5-115">Sono disponibili tre opzioni: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, e <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="bc5f5-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc5f5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc5f5-116">See Also</span></span>  
 [<span data-ttu-id="bc5f5-117">Controllo Panel</span><span class="sxs-lookup"><span data-stu-id="bc5f5-117">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="bc5f5-118">Panoramica sul controllo Panel</span><span class="sxs-lookup"><span data-stu-id="bc5f5-118">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="bc5f5-119">Procedura: Impostare lo sfondo di un controllo Panel</span><span class="sxs-lookup"><span data-stu-id="bc5f5-119">How to: Set the Background of a Panel</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
