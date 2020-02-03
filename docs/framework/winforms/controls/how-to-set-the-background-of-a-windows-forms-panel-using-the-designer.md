---
title: Impostare lo sfondo di un pannello utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731927"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="537d2-102">Procedura: impostare lo sfondo di un pannello di Windows Forms utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="537d2-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="537d2-103">Un controllo Windows Forms <xref:System.Windows.Forms.Panel> può visualizzare sia un colore di sfondo che un'immagine di sfondo.</span><span class="sxs-lookup"><span data-stu-id="537d2-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="537d2-104">La proprietà <xref:System.Windows.Forms.Control.BackColor%2A> imposta il colore di sfondo per i controlli contenuti nel pannello, ad esempio etichette e pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="537d2-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="537d2-105">Se la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, la selezione <xref:System.Windows.Forms.Control.BackColor%2A> compilerà tutto il pannello.</span><span class="sxs-lookup"><span data-stu-id="537d2-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="537d2-106">Se la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, l'immagine verrà visualizzata dietro i controlli contenuti nel pannello.</span><span class="sxs-lookup"><span data-stu-id="537d2-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="537d2-107">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo che contiene un controllo <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="537d2-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="537d2-108">Per informazioni su come configurare tale progetto in Visual Studio, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="537d2-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="537d2-109">Impostare lo sfondo nell'Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="537d2-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="537d2-110">Aprire il progetto in Visual Studio e selezionare il controllo <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="537d2-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="537d2-111">Nella finestra **Proprietà** fare clic sul pulsante freccia accanto alla proprietà <xref:System.Windows.Forms.Control.BackColor%2A> per visualizzare una finestra con tre schede.</span><span class="sxs-lookup"><span data-stu-id="537d2-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="537d2-112">Selezionare la scheda **personalizzata** per visualizzare una tavolozza di colori.</span><span class="sxs-lookup"><span data-stu-id="537d2-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="537d2-113">Selezionare la scheda **Web** o **sistema** per visualizzare un elenco di nomi predefiniti per i colori, quindi selezionare un colore.</span><span class="sxs-lookup"><span data-stu-id="537d2-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="537d2-114">Nella finestra **Proprietà** fare clic sul pulsante freccia accanto alla proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A>.</span><span class="sxs-lookup"><span data-stu-id="537d2-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="537d2-115">Nella finestra di dialogo **Apri** selezionare il file che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="537d2-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="537d2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="537d2-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="537d2-117">Controllo Panel</span><span class="sxs-lookup"><span data-stu-id="537d2-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="537d2-118">Panoramica sul controllo Panel</span><span class="sxs-lookup"><span data-stu-id="537d2-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="537d2-119">Procedura: Raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="537d2-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
