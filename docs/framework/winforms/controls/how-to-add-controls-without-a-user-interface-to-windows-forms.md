---
title: 'Procedura: Aggiungere controlli senza interfaccia utente a un Windows Form'
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
ms.openlocfilehash: 442a6175b1b378cf3489314e190c58312a327c01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738589"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="ad3ee-102">Procedura: Aggiungere controlli senza interfaccia utente a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad3ee-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="ad3ee-103">Un controllo non visivo (o componente) offre funzionalità all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="ad3ee-104">A differenza di altri controlli, componenti non forniscono un'interfaccia utente per l'utente e pertanto non sono necessario essere visualizzato nell'area di progettazione di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="ad3ee-105">Quando un componente viene aggiunto a un form, finestra di progettazione Windows Form consente di visualizzare una barra delle applicazioni ridimensionabile nella parte inferiore del form in cui vengono visualizzati tutti i componenti.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="ad3ee-106">Dopo aver aggiunto un controllo alla barra dei componenti, è possibile selezionare il componente e impostarne le proprietà come si farebbe con qualsiasi altro controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad3ee-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ad3ee-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="ad3ee-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ad3ee-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ad3ee-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="ad3ee-110">Per aggiungere un componente a un modulo di Windows</span><span class="sxs-lookup"><span data-stu-id="ad3ee-110">To add a component to a Windows Form</span></span>  
  
1.  <span data-ttu-id="ad3ee-111">Aprire il form.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-111">Open the form.</span></span> <span data-ttu-id="ad3ee-112">Per informazioni dettagliate, vedere [come: Visualizzare Windows Form nella finestra di progettazione](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span><span class="sxs-lookup"><span data-stu-id="ad3ee-112">For details, see [How to: Display Windows Forms in the Designer](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="ad3ee-113">Nel **casella degli strumenti**, fare clic su un componente e trascinarla al form.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="ad3ee-114">Il componente viene visualizzato nella barra dei componenti.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="ad3ee-115">Inoltre, i componenti possono essere aggiunti a un form in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="ad3ee-116">Questo è uno scenario comune, soprattutto perché i componenti non è un'espressione visual, a differenza dei controlli che hanno un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="ad3ee-117">Nell'esempio seguente, un <xref:System.Windows.Forms.Timer> componente viene aggiunto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="ad3ee-118">(Si noti che Visual Studio contiene un numero di timer diverso; in questo caso, usare un controllo Windows Form <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-118">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="ad3ee-119">Per altre informazioni sui diversi timer in Visual Studio, vedere [Introduzione ai timer basati su Server](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span><span class="sxs-lookup"><span data-stu-id="ad3ee-119">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ad3ee-120">I componenti hanno spesso specifico del controllo proprietà che deve essere impostata per il componente garantire il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="ad3ee-121">Nel caso del <xref:System.Windows.Forms.Timer> componenti elencati di seguito, si imposta il `Interval` proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="ad3ee-122">Assicurarsi che, quando si aggiungono componenti al progetto, impostare le proprietà necessarie per il componente.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="ad3ee-123">Per aggiungere un componente a un Windows Form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="ad3ee-123">To add a component to a Windows Form programmatically</span></span>  
  
1.  <span data-ttu-id="ad3ee-124">Creare un'istanza di <xref:System.Windows.Forms.Timer> classe nel codice.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2.  <span data-ttu-id="ad3ee-125">Impostare il `Interval` proprietà per determinare il tempo tra i segni di graduazione del timer.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3.  <span data-ttu-id="ad3ee-126">Configurare le altre proprietà necessarie per il componente.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="ad3ee-127">Il codice seguente illustra la creazione di un <xref:System.Windows.Forms.Timer> con relativo `Interval` set di proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
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
    >  <span data-ttu-id="ad3ee-128">Facendo riferimento a un controllo utente malintenzionato può esporre il computer locale a un rischio per la sicurezza attraverso la rete.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="ad3ee-129">Questa è solo un problema nel caso di un utente con un controllo personalizzato, seguito dall'utente erroneamente aggiungendolo al progetto.</span><span class="sxs-lookup"><span data-stu-id="ad3ee-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3ee-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad3ee-130">See also</span></span>
- [<span data-ttu-id="ad3ee-131">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad3ee-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
- [<span data-ttu-id="ad3ee-132">Procedura: Aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad3ee-132">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="ad3ee-133">Procedura: Aggiungere i controlli ActiveX a Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad3ee-133">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="ad3ee-134">Procedura: Copiare i controlli tra Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad3ee-134">How to: Copy Controls Between Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)
- [<span data-ttu-id="ad3ee-135">Inserimento di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad3ee-135">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
- [<span data-ttu-id="ad3ee-136">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="ad3ee-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="ad3ee-137">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad3ee-137">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="ad3ee-138">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="ad3ee-138">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
