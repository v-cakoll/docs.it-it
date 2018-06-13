---
title: 'Procedura: ereditare da controlli di Windows Form esistenti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 6f35881bdb7a781d817c9f671962d0445bfd8e27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538741"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="d83bb-102">Procedura: ereditare da controlli di Windows Form esistenti</span><span class="sxs-lookup"><span data-stu-id="d83bb-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="d83bb-103">Se si desidera estendere le funzionalità di un controllo esistente, è possibile creare un controllo derivato da un controllo esistente tramite l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="d83bb-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="d83bb-104">Quando si eredita da un controllo esistente, si ereditano tutte le funzionalità e le proprietà visive di tale controllo.</span><span class="sxs-lookup"><span data-stu-id="d83bb-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="d83bb-105">Ad esempio, se si crea un controllo che eredita da <xref:System.Windows.Forms.Button>, il nuovo controllo avrà un aspetto e funzionano esattamente come standard <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="d83bb-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="d83bb-106">È quindi possibile estendere o modificare la funzionalità del nuovo controllo tramite l'implementazione di metodi e proprietà personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d83bb-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="d83bb-107">In alcuni controlli, è anche possibile modificare l'aspetto visivo del controllo ereditato eseguendo l'override relativo <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="d83bb-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d83bb-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="d83bb-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d83bb-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="d83bb-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d83bb-110">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="d83bb-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-inherited-control"></a><span data-ttu-id="d83bb-111">Per creare un controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="d83bb-111">To create an inherited control</span></span>  
  
1.  <span data-ttu-id="d83bb-112">Creare un nuovo progetto di **Applicazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="d83bb-112">Create a new **Windows Forms Application** project.</span></span>  
  
2.  <span data-ttu-id="d83bb-113">Dal menu **Progetto**, scegliere **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d83bb-113">From the **Project** menu, choose **Add New Item**.</span></span>  
  
     <span data-ttu-id="d83bb-114">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d83bb-114">The **Add New Item** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="d83bb-115">Nella finestra di dialogo **Aggiungi nuovo elemento**, fare doppio clic su **Controllo personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="d83bb-115">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>  
  
     <span data-ttu-id="d83bb-116">Un nuovo controllo personalizzato viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="d83bb-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="d83bb-117">Se si usa Visual Basic, nella parte in alto di **Esplora soluzioni**, fare clic su **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="d83bb-117">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="d83bb-118">Espandere CustomControl1.vb e quindi aprire Customcontrol1 nell'Editor di codice.</span><span class="sxs-lookup"><span data-stu-id="d83bb-118">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>  
  
5.  <span data-ttu-id="d83bb-119">Se si usa C#, aprire CustomControl1.cs nell'Editor di codice.</span><span class="sxs-lookup"><span data-stu-id="d83bb-119">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>  
  
6.  <span data-ttu-id="d83bb-120">Individuare la dichiarazione di classe che eredita da <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="d83bb-120">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>  
  
7.  <span data-ttu-id="d83bb-121">Modificare la classe di base per il controllo da cui si desidera ereditare.</span><span class="sxs-lookup"><span data-stu-id="d83bb-121">Change the base class to the control that you want to inherit from.</span></span>  
  
     <span data-ttu-id="d83bb-122">Ad esempio, se si desidera ereditare <xref:System.Windows.Forms.Button>, modificare la dichiarazione di classe per le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d83bb-122">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  <span data-ttu-id="d83bb-123">Se si usa Visual Basic, salvare e chiudere CustomControl1.Designer.vb.</span><span class="sxs-lookup"><span data-stu-id="d83bb-123">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="d83bb-124">Aprire Customcontrol1.vb nell'Editor di codice.</span><span class="sxs-lookup"><span data-stu-id="d83bb-124">Open CustomControl1.vb in the Code Editor.</span></span>  
  
9. <span data-ttu-id="d83bb-125">Implementare eventuali metodi o proprietà personalizzati da incorporare nel controllo.</span><span class="sxs-lookup"><span data-stu-id="d83bb-125">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
10. <span data-ttu-id="d83bb-126">Se si desidera modificare l'aspetto grafico del controllo, eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="d83bb-126">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d83bb-127">Si esegue l'override <xref:System.Windows.Forms.Control.OnPaint%2A> non consente di modificare l'aspetto di tutti i controlli.</span><span class="sxs-lookup"><span data-stu-id="d83bb-127">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="d83bb-128">I controlli che hanno tutti il disegno eseguito da Windows (ad esempio, <xref:System.Windows.Forms.TextBox>) non chiamano mai loro <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo) e pertanto non verrà mai utilizzare codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d83bb-128">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="d83bb-129">Fare riferimento alla documentazione della Guida per il controllo specifico che si desidera modificare per vedere se il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d83bb-129">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="d83bb-130">Per un elenco di tutti i controlli Windows Forms vedere [Controlli da usare in Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d83bb-130">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="d83bb-131">Se non dispone di un controllo <xref:System.Windows.Forms.Control.OnPaint%2A> elencato come un metodo di membro, non è possibile modificare l'aspetto eseguendo l'override di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="d83bb-131">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="d83bb-132">Per altre informazioni sul disegno personalizzato, vedere [Disegno e rendering di controlli personalizzati](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="d83bb-132">For more information about custom painting, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. <span data-ttu-id="d83bb-133">Salvare ed eseguire il test del controllo.</span><span class="sxs-lookup"><span data-stu-id="d83bb-133">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d83bb-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d83bb-134">See Also</span></span>  
 [<span data-ttu-id="d83bb-135">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="d83bb-135">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="d83bb-136">Procedura: Ereditare dalla classe Control</span><span class="sxs-lookup"><span data-stu-id="d83bb-136">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="d83bb-137">Procedura: Ereditare dalla classe UserControl</span><span class="sxs-lookup"><span data-stu-id="d83bb-137">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="d83bb-138">Procedura: Creare controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="d83bb-138">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="d83bb-139">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d83bb-139">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="d83bb-140">Procedura dettagliata: Eredità da un controllo Windows Form con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d83bb-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="d83bb-141">Procedura dettagliata: eredità da un controllo di Windows Forms con Visual C#</span><span class="sxs-lookup"><span data-stu-id="d83bb-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
