---
title: Aggiungere controlli senza interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 43f13b4f009fcd6e5d82fa2c00113a77d48877b6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744748"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="6a374-102">Procedura: aggiungere controlli senza interfaccia a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="6a374-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>

<span data-ttu-id="6a374-103">Un controllo o un componente non visivo fornisce funzionalità per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6a374-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="6a374-104">A differenza di altri controlli, i componenti non forniscono un'interfaccia utente per l'utente e pertanto non devono essere visualizzati nell'area di Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6a374-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="6a374-105">Quando un componente viene aggiunto a un modulo, il Progettazione Windows Form Visualizza un vassoio ridimensionabile nella parte inferiore del form in cui vengono visualizzati tutti i componenti.</span><span class="sxs-lookup"><span data-stu-id="6a374-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="6a374-106">Dopo che un controllo è stato aggiunto alla barra dei componenti, è possibile selezionare il componente e impostarne le proprietà come qualsiasi altro controllo del modulo.</span><span class="sxs-lookup"><span data-stu-id="6a374-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>

## <a name="add-a-component-to-a-windows-form"></a><span data-ttu-id="6a374-107">Aggiungere un componente a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="6a374-107">Add a component to a Windows Form</span></span>

1. <span data-ttu-id="6a374-108">Aprire il modulo in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6a374-108">Open the form in Visual Studio.</span></span> <span data-ttu-id="6a374-109">Per informazioni dettagliate, vedere [procedura: visualizzare Windows Forms nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6a374-109">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="6a374-110">Nella **casella degli strumenti**fare clic su un componente e trascinarlo nel form.</span><span class="sxs-lookup"><span data-stu-id="6a374-110">In the **Toolbox**, click a component and drag it to your form.</span></span>

     <span data-ttu-id="6a374-111">Il componente verrà visualizzato nella barra dei componenti.</span><span class="sxs-lookup"><span data-stu-id="6a374-111">Your component appears in the component tray.</span></span>

<span data-ttu-id="6a374-112">Inoltre, i componenti possono essere aggiunti a un modulo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6a374-112">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="6a374-113">Si tratta di uno scenario comune, soprattutto perché i componenti non hanno un'espressione visiva, a differenza dei controlli che hanno un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6a374-113">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="6a374-114">Nell'esempio seguente viene aggiunto un componente <xref:System.Windows.Forms.Timer> in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6a374-114">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="6a374-115">Si noti che Visual Studio contiene una serie di timer diversi. in questo caso, usare un componente Windows Forms <xref:System.Windows.Forms.Timer>.</span><span class="sxs-lookup"><span data-stu-id="6a374-115">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="6a374-116">Per ulteriori informazioni sui diversi timer in Visual Studio, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="6a374-116">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>

> [!CAUTION]
> <span data-ttu-id="6a374-117">I componenti presentano spesso proprietà specifiche del controllo che è necessario impostare affinché il componente funzioni in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="6a374-117">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="6a374-118">Nel caso del componente <xref:System.Windows.Forms.Timer> riportato di seguito, impostare la proprietà `Interval`.</span><span class="sxs-lookup"><span data-stu-id="6a374-118">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="6a374-119">Assicurarsi che, quando si aggiungono componenti al progetto, si impostano le proprietà necessarie per quel componente.</span><span class="sxs-lookup"><span data-stu-id="6a374-119">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>

## <a name="add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="6a374-120">Aggiungere un componente a un Windows Form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="6a374-120">Add a component to a Windows Form programmatically</span></span>

1. <span data-ttu-id="6a374-121">Creare un'istanza della classe <xref:System.Windows.Forms.Timer> nel codice.</span><span class="sxs-lookup"><span data-stu-id="6a374-121">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>

2. <span data-ttu-id="6a374-122">Impostare la proprietà `Interval` per determinare l'intervallo di tempo tra i cicli del timer.</span><span class="sxs-lookup"><span data-stu-id="6a374-122">Set the `Interval` property to determine the time between ticks of the timer.</span></span>

3. <span data-ttu-id="6a374-123">Configurare qualsiasi altra proprietà necessaria per il componente.</span><span class="sxs-lookup"><span data-stu-id="6a374-123">Configure any other necessary properties for your component.</span></span>

     <span data-ttu-id="6a374-124">Nel codice seguente viene illustrata la creazione di un <xref:System.Windows.Forms.Timer> con il relativo set di proprietà `Interval`.</span><span class="sxs-lookup"><span data-stu-id="6a374-124">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>

    ```vb
    Public Sub CreateTimer()
       Dim timerKeepTrack As New System.Windows.Forms.Timer
       timerKeepTrack.Interval = 1000
    End Sub
    ```

    ```csharp
    public void createTimer()
    {
       System.Windows.Forms.Timer timerKeepTrack = new
           System.Windows.Forms.Timer();
       timerKeepTrack.Interval = 1000;
    }
    ```

    ```cpp
    public:
       void createTimer()
       {
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew
             System::Windows::Forms::Timer();
          timerKeepTrack->Interval = 1000;
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="6a374-125">È possibile esporre il computer locale a un rischio di sicurezza attraverso la rete facendo riferimento a un UserControl dannoso.</span><span class="sxs-lookup"><span data-stu-id="6a374-125">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="6a374-126">Questo potrebbe costituire un problema solo nel caso di un utente malintenzionato che crea un controllo personalizzato dannoso, seguito da un'operazione erroneamente aggiunta al progetto.</span><span class="sxs-lookup"><span data-stu-id="6a374-126">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a374-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a374-127">See also</span></span>

- [<span data-ttu-id="6a374-128">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6a374-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="6a374-129">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a374-129">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="6a374-130">Procedura: Aggiungere i controlli ActiveX a Windows Form</span><span class="sxs-lookup"><span data-stu-id="6a374-130">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="6a374-131">Inserimento di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6a374-131">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="6a374-132">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="6a374-132">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="6a374-133">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6a374-133">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="6a374-134">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="6a374-134">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
