---
title: 'Procedura: posizionare i controlli in Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ff1096e6397f4422e0fbf6400a87041cfac6470
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="1f979-102">Procedura: posizionare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1f979-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="1f979-103">Per posizionare i controlli, utilizzare la finestra di progettazione Windows Form o specificare il <xref:System.Windows.Forms.Control.Location%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1f979-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f979-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="1f979-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1f979-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="1f979-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1f979-106">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="1f979-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="1f979-107">Per posizionare un controllo nella finestra di progettazione di progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="1f979-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="1f979-108">Trascinare il controllo nella posizione appropriata con il mouse.</span><span class="sxs-lookup"><span data-stu-id="1f979-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f979-109">Selezionare il controllo e spostare che con i tasti di direzione per un posizionamento più preciso.</span><span class="sxs-lookup"><span data-stu-id="1f979-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="1f979-110">Inoltre, *le guide di allineamento* supporto per il posizionamento accurato dei controlli del form.</span><span class="sxs-lookup"><span data-stu-id="1f979-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="1f979-111">Per ulteriori informazioni, vedere [procedura dettagliata: disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="1f979-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="1f979-112">Per posizionare un controllo utilizzando la finestra proprietà</span><span class="sxs-lookup"><span data-stu-id="1f979-112">To position a control using the Properties window</span></span>  
  
1.  <span data-ttu-id="1f979-113">Fare clic per posizionare il controllo.</span><span class="sxs-lookup"><span data-stu-id="1f979-113">Click the control you want to position.</span></span>  
  
2.  <span data-ttu-id="1f979-114">Nel **proprietà** finestra, digitare i valori per il <xref:System.Windows.Forms.Control.Location%2A> proprietà, separati da una virgola, per posizionare il controllo all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="1f979-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="1f979-115">Il primo numero (X) rappresenta la distanza dal bordo sinistro del contenitore; il secondo numero (Y) è la distanza dal bordo superiore dell'area del contenitore, misurata in pixel.</span><span class="sxs-lookup"><span data-stu-id="1f979-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f979-116">È possibile espandere il <xref:System.Windows.Forms.Control.Location%2A> proprietà al tipo di **X** e **Y** valori singolarmente.</span><span class="sxs-lookup"><span data-stu-id="1f979-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="1f979-117">Per posizionare un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="1f979-117">To position a control programmatically</span></span>  
  
1.  <span data-ttu-id="1f979-118">Impostare il <xref:System.Windows.Forms.Control.Location%2A> proprietà del controllo da un <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="1f979-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  <span data-ttu-id="1f979-119">Modificare la coordinata X della posizione del controllo utilizzando il <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà.</span><span class="sxs-lookup"><span data-stu-id="1f979-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="1f979-120">Per incrementare la posizione di un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="1f979-120">To increment a control's location programmatically</span></span>  
  
1.  <span data-ttu-id="1f979-121">Impostare il <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà per incrementare la coordinata X del controllo.</span><span class="sxs-lookup"><span data-stu-id="1f979-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
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
    >  <span data-ttu-id="1f979-122">Utilizzare il <xref:System.Windows.Forms.Control.Location%2A> contemporaneamente le posizioni di proprietà per impostare un controllo X e Y.</span><span class="sxs-lookup"><span data-stu-id="1f979-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="1f979-123">Per impostare una posizione singolarmente, utilizzare il controllo <xref:System.Windows.Forms.Control.Left%2A> (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**) sottoproprietà.</span><span class="sxs-lookup"><span data-stu-id="1f979-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="1f979-124">Non tentare di impostare in modo implicito le coordinate X e Y del <xref:System.Drawing.Point> struttura che rappresenta la posizione del pulsante, poiché tale struttura contiene una copia delle coordinate del pulsante.</span><span class="sxs-lookup"><span data-stu-id="1f979-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f979-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f979-125">See Also</span></span>  
 [<span data-ttu-id="1f979-126">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="1f979-126">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="1f979-127">Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="1f979-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="1f979-128">Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="1f979-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="1f979-129">Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="1f979-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="1f979-130">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1f979-130">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="1f979-131">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="1f979-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="1f979-132">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1f979-132">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="1f979-133">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="1f979-133">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="1f979-134">Procedura: impostare la posizione dello schermo dei Windows Form</span><span class="sxs-lookup"><span data-stu-id="1f979-134">How to: Set the Screen Location of Windows Forms</span></span>](http://msdn.microsoft.com/en-us/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
