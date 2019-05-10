---
title: 'Procedura: Impostare lo sfondo di un controllo Panel di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 6927a7118c43ced03623a9764a3ef1e0814c95cb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211635"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="f61ec-102">Procedura: Impostare lo sfondo di un controllo panel Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f61ec-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="f61ec-103">Un controllo Windows Form <xref:System.Windows.Forms.Panel> controllo può visualizzare un colore di sfondo sia un'immagine di sfondo.</span><span class="sxs-lookup"><span data-stu-id="f61ec-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="f61ec-104">Il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà imposta il colore di sfondo per i controlli che sono contenuti nel pannello, ad esempio le etichette e i pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="f61ec-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="f61ec-105">Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, il <xref:System.Windows.Forms.Control.BackColor%2A> compilerà tutte del Pannello di selezione.</span><span class="sxs-lookup"><span data-stu-id="f61ec-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="f61ec-106">Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, verrà visualizzata l'immagine dietro i controlli contenuti nel pannello.</span><span class="sxs-lookup"><span data-stu-id="f61ec-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="f61ec-107">La procedura seguente richiede un **applicazione di Windows** progetto con un modulo che contiene un <xref:System.Windows.Forms.Panel> controllo.</span><span class="sxs-lookup"><span data-stu-id="f61ec-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="f61ec-108">Per informazioni su come configurare tali progetti in Visual Studio, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f61ec-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="f61ec-109">Impostare lo sfondo in Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="f61ec-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="f61ec-110">Aprire il progetto in Visual Studio e selezionare il <xref:System.Windows.Forms.Panel> controllo.</span><span class="sxs-lookup"><span data-stu-id="f61ec-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="f61ec-111">Nel **delle proprietà** fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackColor%2A> proprietà per visualizzare una finestra con tre schede.</span><span class="sxs-lookup"><span data-stu-id="f61ec-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="f61ec-112">Selezionare il **Custom** pressione di tab per visualizzare una tavolozza dei colori.</span><span class="sxs-lookup"><span data-stu-id="f61ec-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="f61ec-113">Selezionare il **Web** oppure **sistema** scheda per visualizzare un elenco di nomi predefiniti per i colori e quindi selezionare un colore.</span><span class="sxs-lookup"><span data-stu-id="f61ec-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="f61ec-114">Nel **delle proprietà** fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f61ec-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="f61ec-115">Nel **aperto** finestra di dialogo, selezionare il file che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="f61ec-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="f61ec-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f61ec-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="f61ec-117">Controllo Panel</span><span class="sxs-lookup"><span data-stu-id="f61ec-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="f61ec-118">Panoramica sul controllo Panel</span><span class="sxs-lookup"><span data-stu-id="f61ec-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="f61ec-119">Procedura: Controlli di gruppo con il controllo Panel di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f61ec-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
