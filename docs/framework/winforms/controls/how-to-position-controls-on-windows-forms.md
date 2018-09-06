---
title: 'Procedura: posizionare i controlli in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: 6843c22fec964de92c41760f1108d1c83e1f5bf8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43871176"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="c4dfd-102">Procedura: posizionare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c4dfd-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="c4dfd-103">Per posizionare i controlli, usare Progettazione Windows Form o specificare il <xref:System.Windows.Forms.Control.Location%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4dfd-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c4dfd-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c4dfd-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c4dfd-106">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c4dfd-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="c4dfd-107">Per posizionare un controllo nell'area di progettazione della finestra di progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="c4dfd-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="c4dfd-108">Trascinare il controllo nella posizione appropriata con il mouse.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4dfd-109">Selezionare il controllo e spostarsi che con la freccia tasti di direzione per un posizionamento più preciso.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="c4dfd-110">È inoltre *guide di allineamento* supporto per il posizionamento preciso dei controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="c4dfd-111">Per altre informazioni, vedere [procedura dettagliata: disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="c4dfd-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="c4dfd-112">Per posizionare un controllo usando la finestra proprietà</span><span class="sxs-lookup"><span data-stu-id="c4dfd-112">To position a control using the Properties window</span></span>  
  
1.  <span data-ttu-id="c4dfd-113">Fare clic sul controllo che si desidera posizionare.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-113">Click the control you want to position.</span></span>  
  
2.  <span data-ttu-id="c4dfd-114">Nel **delle proprietà** finestra, i valori di tipo per il <xref:System.Windows.Forms.Control.Location%2A> proprietà, separati da una virgola, per posizionare il controllo all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="c4dfd-115">Il primo numero (X) rappresenta la distanza dal bordo sinistro del contenitore; il secondo numero (Y) è la distanza dal bordo superiore dell'area del contenitore, misurato in pixel.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4dfd-116">È possibile espandere la <xref:System.Windows.Forms.Control.Location%2A> proprietà digitare il **X** e **Y** valori singolarmente.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="c4dfd-117">Per posizionare un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="c4dfd-117">To position a control programmatically</span></span>  
  
1.  <span data-ttu-id="c4dfd-118">Impostare il <xref:System.Windows.Forms.Control.Location%2A> proprietà del controllo da un <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  <span data-ttu-id="c4dfd-119">Modificare la coordinata X della posizione del controllo utilizzando il <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="c4dfd-120">Per incrementare la posizione di un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="c4dfd-120">To increment a control's location programmatically</span></span>  
  
1.  <span data-ttu-id="c4dfd-121">Impostare il <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà per incrementare la coordinata X del controllo.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c4dfd-122">Usare il <xref:System.Windows.Forms.Control.Location%2A> contemporaneamente le posizioni di proprietà da impostare X e Y di un controllo.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="c4dfd-123">Per impostare una posizione individualmente, usare il controllo <xref:System.Windows.Forms.Control.Left%2A> (**X**) oppure <xref:System.Windows.Forms.Control.Top%2A> (**Y**) delle sottoproprietà.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="c4dfd-124">Non provare a impostare in modo implicito le coordinate X e Y del <xref:System.Drawing.Point> struttura che rappresenta la posizione del pulsante, perché questa struttura contiene una copia di coordinate del pulsante.</span><span class="sxs-lookup"><span data-stu-id="c4dfd-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4dfd-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4dfd-125">See Also</span></span>  
 [<span data-ttu-id="c4dfd-126">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="c4dfd-126">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="c4dfd-127">Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="c4dfd-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="c4dfd-128">Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c4dfd-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="c4dfd-129">Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c4dfd-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="c4dfd-130">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c4dfd-130">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="c4dfd-131">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="c4dfd-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="c4dfd-132">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c4dfd-132">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="c4dfd-133">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="c4dfd-133">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="c4dfd-134">Procedura: impostare la posizione dello schermo dei Windows Form</span><span class="sxs-lookup"><span data-stu-id="c4dfd-134">How to: Set the Screen Location of Windows Forms</span></span>](https://msdn.microsoft.com/library/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
