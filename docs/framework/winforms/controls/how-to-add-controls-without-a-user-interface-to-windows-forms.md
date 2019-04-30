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
ms.openlocfilehash: 0768f811653543b3370310ccc0b59890273baf52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011086"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="72338-102">Procedura: Aggiungere i controlli senza un'interfaccia utente a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72338-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="72338-103">Un controllo non visivo (o componente) offre funzionalità all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="72338-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="72338-104">A differenza di altri controlli, componenti non forniscono un'interfaccia utente per l'utente e pertanto non sono necessario essere visualizzato nell'area di progettazione di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="72338-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="72338-105">Quando un componente viene aggiunto a un form, finestra di progettazione Windows Form consente di visualizzare una barra delle applicazioni ridimensionabile nella parte inferiore del form in cui vengono visualizzati tutti i componenti.</span><span class="sxs-lookup"><span data-stu-id="72338-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="72338-106">Dopo aver aggiunto un controllo alla barra dei componenti, è possibile selezionare il componente e impostarne le proprietà come si farebbe con qualsiasi altro controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="72338-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72338-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="72338-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="72338-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="72338-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="72338-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="72338-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="72338-110">Per aggiungere un componente a un modulo di Windows</span><span class="sxs-lookup"><span data-stu-id="72338-110">To add a component to a Windows Form</span></span>  
  
1. <span data-ttu-id="72338-111">Aprire il form.</span><span class="sxs-lookup"><span data-stu-id="72338-111">Open the form.</span></span> <span data-ttu-id="72338-112">Per informazioni dettagliate, vedere [Procedura: Visualizzare Windows Form nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="72338-112">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="72338-113">Nel **casella degli strumenti**, fare clic su un componente e trascinarla al form.</span><span class="sxs-lookup"><span data-stu-id="72338-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="72338-114">Il componente viene visualizzato nella barra dei componenti.</span><span class="sxs-lookup"><span data-stu-id="72338-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="72338-115">Inoltre, i componenti possono essere aggiunti a un form in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="72338-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="72338-116">Questo è uno scenario comune, soprattutto perché i componenti non è un'espressione visual, a differenza dei controlli che hanno un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="72338-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="72338-117">Nell'esempio seguente, un <xref:System.Windows.Forms.Timer> componente viene aggiunto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="72338-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="72338-118">(Si noti che Visual Studio contiene un numero di timer diverso; in questo caso, usare un controllo Windows Form <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="72338-118">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="72338-119">Per altre informazioni sui diversi timer in Visual Studio, vedere [Introduzione ai timer basati su Server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span><span class="sxs-lookup"><span data-stu-id="72338-119">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="72338-120">I componenti hanno spesso specifico del controllo proprietà che deve essere impostata per il componente garantire il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="72338-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="72338-121">Nel caso del <xref:System.Windows.Forms.Timer> componenti elencati di seguito, si imposta il `Interval` proprietà.</span><span class="sxs-lookup"><span data-stu-id="72338-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="72338-122">Assicurarsi che, quando si aggiungono componenti al progetto, impostare le proprietà necessarie per il componente.</span><span class="sxs-lookup"><span data-stu-id="72338-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="72338-123">Per aggiungere un componente a un Windows Form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="72338-123">To add a component to a Windows Form programmatically</span></span>  
  
1. <span data-ttu-id="72338-124">Creare un'istanza di <xref:System.Windows.Forms.Timer> classe nel codice.</span><span class="sxs-lookup"><span data-stu-id="72338-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2. <span data-ttu-id="72338-125">Impostare il `Interval` proprietà per determinare il tempo tra i segni di graduazione del timer.</span><span class="sxs-lookup"><span data-stu-id="72338-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3. <span data-ttu-id="72338-126">Configurare le altre proprietà necessarie per il componente.</span><span class="sxs-lookup"><span data-stu-id="72338-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="72338-127">Il codice seguente illustra la creazione di un <xref:System.Windows.Forms.Timer> con relativo `Interval` set di proprietà.</span><span class="sxs-lookup"><span data-stu-id="72338-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
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
    >  <span data-ttu-id="72338-128">Facendo riferimento a un controllo utente malintenzionato può esporre il computer locale a un rischio per la sicurezza attraverso la rete.</span><span class="sxs-lookup"><span data-stu-id="72338-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="72338-129">Questa è solo un problema nel caso di un utente con un controllo personalizzato, seguito dall'utente erroneamente aggiungendolo al progetto.</span><span class="sxs-lookup"><span data-stu-id="72338-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72338-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72338-130">See also</span></span>

- [<span data-ttu-id="72338-131">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="72338-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="72338-132">Procedura: Aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="72338-132">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="72338-133">Procedura: Aggiungere i controlli ActiveX a Windows Form</span><span class="sxs-lookup"><span data-stu-id="72338-133">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="72338-134">Procedura: Copiare i controlli tra Windows Form</span><span class="sxs-lookup"><span data-stu-id="72338-134">How to: Copy Controls Between Windows Forms</span></span>](how-to-copy-controls-between-windows-forms.md)
- [<span data-ttu-id="72338-135">Inserimento di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="72338-135">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="72338-136">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="72338-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="72338-137">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="72338-137">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="72338-138">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="72338-138">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
