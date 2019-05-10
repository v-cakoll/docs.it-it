---
title: "Procedura: Aggiungere i controlli senza un'interfaccia utente a Windows Forms"
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
ms.openlocfilehash: 49bf927085d29b60c1d9cf5d61df3894495349db
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210418"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="8c6ce-102">Procedura: Aggiungere i controlli senza un'interfaccia utente a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c6ce-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>

<span data-ttu-id="8c6ce-103">Un controllo non visivo (o componente) offre funzionalità all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="8c6ce-104">A differenza di altri controlli, componenti non forniscono un'interfaccia utente per l'utente e pertanto non sono necessario essere visualizzato nell'area di progettazione di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="8c6ce-105">Quando un componente viene aggiunto a un form, finestra di progettazione Windows Form consente di visualizzare una barra delle applicazioni ridimensionabile nella parte inferiore del form in cui vengono visualizzati tutti i componenti.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="8c6ce-106">Dopo aver aggiunto un controllo alla barra dei componenti, è possibile selezionare il componente e impostarne le proprietà come si farebbe con qualsiasi altro controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>

## <a name="add-a-component-to-a-windows-form"></a><span data-ttu-id="8c6ce-107">Aggiungere un componente a un modulo di Windows</span><span class="sxs-lookup"><span data-stu-id="8c6ce-107">Add a component to a Windows Form</span></span>

1. <span data-ttu-id="8c6ce-108">Aprire il form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-108">Open the form in Visual Studio.</span></span> <span data-ttu-id="8c6ce-109">Per informazioni dettagliate, vedere [Procedura: Visualizzare Windows Form nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8c6ce-109">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="8c6ce-110">Nel **casella degli strumenti**, fare clic su un componente e trascinarla al form.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-110">In the **Toolbox**, click a component and drag it to your form.</span></span>

     <span data-ttu-id="8c6ce-111">Il componente viene visualizzato nella barra dei componenti.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-111">Your component appears in the component tray.</span></span>

<span data-ttu-id="8c6ce-112">Inoltre, i componenti possono essere aggiunti a un form in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-112">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="8c6ce-113">Questo è uno scenario comune, soprattutto perché i componenti non è un'espressione visual, a differenza dei controlli che hanno un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-113">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="8c6ce-114">Nell'esempio seguente, un <xref:System.Windows.Forms.Timer> componente viene aggiunto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-114">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="8c6ce-115">(Si noti che Visual Studio contiene un numero di timer diverso; in questo caso, usare un controllo Windows Form <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-115">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="8c6ce-116">Per altre informazioni sui diversi timer in Visual Studio, vedere [Introduzione ai timer basati su Server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span><span class="sxs-lookup"><span data-stu-id="8c6ce-116">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>

> [!CAUTION]
> <span data-ttu-id="8c6ce-117">I componenti hanno spesso specifico del controllo proprietà che deve essere impostata per il componente garantire il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-117">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="8c6ce-118">Nel caso del <xref:System.Windows.Forms.Timer> componenti elencati di seguito, si imposta il `Interval` proprietà.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-118">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="8c6ce-119">Assicurarsi che, quando si aggiungono componenti al progetto, impostare le proprietà necessarie per il componente.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-119">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>

## <a name="add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="8c6ce-120">Aggiungere un componente a un Windows Form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="8c6ce-120">Add a component to a Windows Form programmatically</span></span>

1. <span data-ttu-id="8c6ce-121">Creare un'istanza di <xref:System.Windows.Forms.Timer> classe nel codice.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-121">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>

2. <span data-ttu-id="8c6ce-122">Impostare il `Interval` proprietà per determinare il tempo tra i segni di graduazione del timer.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-122">Set the `Interval` property to determine the time between ticks of the timer.</span></span>

3. <span data-ttu-id="8c6ce-123">Configurare le altre proprietà necessarie per il componente.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-123">Configure any other necessary properties for your component.</span></span>

     <span data-ttu-id="8c6ce-124">Il codice seguente illustra la creazione di un <xref:System.Windows.Forms.Timer> con relativo `Interval` set di proprietà.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-124">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>

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
    > <span data-ttu-id="8c6ce-125">Facendo riferimento a un controllo utente malintenzionato può esporre il computer locale a un rischio per la sicurezza attraverso la rete.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-125">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="8c6ce-126">Questa è solo un problema nel caso di un utente con un controllo personalizzato, seguito dall'utente erroneamente aggiungendolo al progetto.</span><span class="sxs-lookup"><span data-stu-id="8c6ce-126">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c6ce-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c6ce-127">See also</span></span>

- [<span data-ttu-id="8c6ce-128">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="8c6ce-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="8c6ce-129">Procedura: Aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="8c6ce-129">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="8c6ce-130">Procedura: Aggiungere i controlli ActiveX a Windows Form</span><span class="sxs-lookup"><span data-stu-id="8c6ce-130">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="8c6ce-131">Procedura: Copiare i controlli tra Windows Form</span><span class="sxs-lookup"><span data-stu-id="8c6ce-131">How to: Copy Controls Between Windows Forms</span></span>](how-to-copy-controls-between-windows-forms.md)
- [<span data-ttu-id="8c6ce-132">Inserimento di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8c6ce-132">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="8c6ce-133">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="8c6ce-133">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="8c6ce-134">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8c6ce-134">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="8c6ce-135">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="8c6ce-135">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
