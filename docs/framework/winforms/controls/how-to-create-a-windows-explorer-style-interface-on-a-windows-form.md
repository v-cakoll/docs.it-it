---
title: "Procedura: Creare un'interfaccia di tipo Esplora risorse in un Windows Form"
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 34a5cd735c350688d9e83003806668e213932c85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960619"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="725c4-102">Procedura: Creare un'interfaccia di tipo Esplora risorse in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="725c4-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="725c4-103">Esplora risorse è una scelta di interfaccia utente comune per le applicazioni grazie alla sua dimestichezza.</span><span class="sxs-lookup"><span data-stu-id="725c4-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>

 <span data-ttu-id="725c4-104">Esplora risorse è essenzialmente un <xref:System.Windows.Forms.TreeView> controllo e un <xref:System.Windows.Forms.ListView> controllo su pannelli distinti.</span><span class="sxs-lookup"><span data-stu-id="725c4-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="725c4-105">I pannelli vengono resi ridimensionabili da una barra di divisione.</span><span class="sxs-lookup"><span data-stu-id="725c4-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="725c4-106">Questa disposizione dei controlli è molto efficace per la visualizzazione e l'esplorazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="725c4-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>

 <span data-ttu-id="725c4-107">Nei passaggi seguenti viene illustrato come disporre i controlli in un form di tipo Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="725c4-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="725c4-108">Non illustrano come aggiungere la funzionalità di esplorazione dei file dell'applicazione Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="725c4-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>

## <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="725c4-109">Per creare un Windows Form di tipo Esplora risorse</span><span class="sxs-lookup"><span data-stu-id="725c4-109">To create a Windows Explorer-style Windows Form</span></span>

1. <span data-ttu-id="725c4-110">Creare un nuovo progetto di applicazione Windows (**file** > **nuovo** > **progetto** >  **C# Visual** o **Visual Basic** > **desktop classico**  >  **Applicazione Windows Forms**).</span><span class="sxs-lookup"><span data-stu-id="725c4-110">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="725c4-111">Dalla **casella degli strumenti**:</span><span class="sxs-lookup"><span data-stu-id="725c4-111">From the **Toolbox**:</span></span>

    1. <span data-ttu-id="725c4-112">Trascinare un <xref:System.Windows.Forms.SplitContainer> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="725c4-112">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>

    2. <span data-ttu-id="725c4-113">Trascinare un <xref:System.Windows.Forms.TreeView> controllo in **splitterPanel1** ( <xref:System.Windows.Forms.SplitContainer> il pannello del controllo contrassegnato come **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="725c4-113">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>

    3. <span data-ttu-id="725c4-114">Trascinare un <xref:System.Windows.Forms.ListView> controllo in **splitterPanel2** ( <xref:System.Windows.Forms.SplitContainer> il pannello del controllo contrassegnato come **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="725c4-114">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>

3. <span data-ttu-id="725c4-115">Selezionare tutti e tre i controlli premendo il tasto CTRL e facendo clic su di essi a sua volta.</span><span class="sxs-lookup"><span data-stu-id="725c4-115">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="725c4-116">Quando si seleziona il <xref:System.Windows.Forms.SplitContainer> controllo, fare clic sulla barra di divisione anziché sui pannelli.</span><span class="sxs-lookup"><span data-stu-id="725c4-116">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="725c4-117">Non utilizzare il comando **Seleziona tutto** nel menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="725c4-117">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="725c4-118">In tal caso, la proprietà necessaria nel passaggio successivo non verrà visualizzata nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="725c4-118">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>

4. <span data-ttu-id="725c4-119">Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="725c4-119">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="725c4-120">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="725c4-120">Press F5 to run the application.</span></span>

     <span data-ttu-id="725c4-121">Il modulo Visualizza un'interfaccia utente in due parti, simile a quella di Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="725c4-121">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="725c4-122">Quando si trascina la barra di divisione, i pannelli si ridimensionano.</span><span class="sxs-lookup"><span data-stu-id="725c4-122">When you drag the splitter, the panels resize themselves.</span></span>

## <a name="see-also"></a><span data-ttu-id="725c4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="725c4-123">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="725c4-124">Procedura: Creare un'interfaccia utente a più riquadri con Windows Forms</span><span class="sxs-lookup"><span data-stu-id="725c4-124">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="725c4-125">Procedura: Definire il comportamento di ridimensionamento e posizionamento in una finestra divisa</span><span class="sxs-lookup"><span data-stu-id="725c4-125">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="725c4-126">Procedura: Suddividere una finestra orizzontalmente</span><span class="sxs-lookup"><span data-stu-id="725c4-126">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="725c4-127">Controllo SplitContainer</span><span class="sxs-lookup"><span data-stu-id="725c4-127">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
