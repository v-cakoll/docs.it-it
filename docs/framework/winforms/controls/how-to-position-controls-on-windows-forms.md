---
title: 'Procedura: Posizionare i controlli in Windows Forms'
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
ms.openlocfilehash: 241edbe60c327493c9123c6cf7bdc19b7ba2b724
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211645"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="6e86a-102">Procedura: Posizionare i controlli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6e86a-102">How to: Position Controls on Windows Forms</span></span>

<span data-ttu-id="6e86a-103">Per posizionare i controlli, usare la finestra di progettazione Windows Form in Visual Studio o specificare il <xref:System.Windows.Forms.Control.Location%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="6e86a-103">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="6e86a-104">Posizionare un controllo nell'area di progettazione della finestra di progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="6e86a-104">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="6e86a-105">In Visual Studio, trascinare il controllo nella posizione appropriata con il mouse.</span><span class="sxs-lookup"><span data-stu-id="6e86a-105">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="6e86a-106">Selezionare il controllo e spostarsi che con la freccia tasti di direzione per un posizionamento più preciso.</span><span class="sxs-lookup"><span data-stu-id="6e86a-106">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="6e86a-107">È inoltre *guide di allineamento* supporto per il posizionamento preciso dei controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="6e86a-107">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="6e86a-108">Per altre informazioni, vedere [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="6e86a-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="6e86a-109">Posizionare un controllo usando la finestra proprietà</span><span class="sxs-lookup"><span data-stu-id="6e86a-109">Position a control using the Properties window</span></span>

1. <span data-ttu-id="6e86a-110">In Visual Studio, fare clic sul controllo che si desidera posizionare.</span><span class="sxs-lookup"><span data-stu-id="6e86a-110">In Visual Studio, click the control you want to position.</span></span>

2. <span data-ttu-id="6e86a-111">Nel **delle proprietà** finestra, i valori di tipo per il <xref:System.Windows.Forms.Control.Location%2A> proprietà, separati da una virgola, per posizionare il controllo all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="6e86a-111">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

     <span data-ttu-id="6e86a-112">Il primo numero (X) rappresenta la distanza dal bordo sinistro del contenitore; il secondo numero (Y) è la distanza dal bordo superiore dell'area del contenitore, misurato in pixel.</span><span class="sxs-lookup"><span data-stu-id="6e86a-112">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6e86a-113">È possibile espandere la <xref:System.Windows.Forms.Control.Location%2A> proprietà digitare il **X** e **Y** valori singolarmente.</span><span class="sxs-lookup"><span data-stu-id="6e86a-113">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="6e86a-114">Posizionare un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="6e86a-114">Position a control programmatically</span></span>

1. <span data-ttu-id="6e86a-115">Impostare il <xref:System.Windows.Forms.Control.Location%2A> proprietà del controllo da un <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="6e86a-115">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="6e86a-116">Modificare la coordinata X della posizione del controllo utilizzando il <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà.</span><span class="sxs-lookup"><span data-stu-id="6e86a-116">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="6e86a-117">Incrementa la posizione di un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="6e86a-117">Increment a control's location programmatically</span></span>

<span data-ttu-id="6e86a-118">Impostare il <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà per incrementare la coordinata X del controllo.</span><span class="sxs-lookup"><span data-stu-id="6e86a-118">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

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
> <span data-ttu-id="6e86a-119">Usare il <xref:System.Windows.Forms.Control.Location%2A> contemporaneamente le posizioni di proprietà da impostare X e Y di un controllo.</span><span class="sxs-lookup"><span data-stu-id="6e86a-119">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="6e86a-120">Per impostare una posizione individualmente, usare il controllo <xref:System.Windows.Forms.Control.Left%2A> (**X**) oppure <xref:System.Windows.Forms.Control.Top%2A> (**Y**) delle sottoproprietà.</span><span class="sxs-lookup"><span data-stu-id="6e86a-120">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="6e86a-121">Non provare a impostare in modo implicito le coordinate X e Y del <xref:System.Drawing.Point> struttura che rappresenta la posizione del pulsante, perché questa struttura contiene una copia di coordinate del pulsante.</span><span class="sxs-lookup"><span data-stu-id="6e86a-121">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e86a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e86a-122">See also</span></span>

- [<span data-ttu-id="6e86a-123">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6e86a-123">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="6e86a-124">Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="6e86a-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="6e86a-125">Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6e86a-125">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="6e86a-126">Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6e86a-126">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="6e86a-127">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6e86a-127">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="6e86a-128">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="6e86a-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="6e86a-129">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6e86a-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="6e86a-130">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="6e86a-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="6e86a-131">[Procedura: Impostare la posizione dello schermo dei Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6e86a-131">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
