---
title: 'Procedura: disporre oggetti su più livelli in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: d67d9b204c316dce5f3818496d791ed4c1b352f2
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46000700"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="1385a-102">Procedura: disporre oggetti su più livelli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1385a-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="1385a-103">Quando si crea un'interfaccia utente complessa, o di lavoro con un form MDI (interfaccia), spesso si desidera sia form e controlli figlio per creare più complesse interfacce utente (UI) di livello.</span><span class="sxs-lookup"><span data-stu-id="1385a-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="1385a-104">Per spostare e tenere traccia di controlli e finestre all'interno del contesto di un gruppo, è modificare l'ordine z.</span><span class="sxs-lookup"><span data-stu-id="1385a-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="1385a-105">*Ordine Z* è disposizione visiva di controlli in un form lungo l'asse z del form (profondità).</span><span class="sxs-lookup"><span data-stu-id="1385a-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="1385a-106">La finestra nella parte superiore dello z-order si sovrappone a tutte le altre finestre.</span><span class="sxs-lookup"><span data-stu-id="1385a-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="1385a-107">Tutte le altre finestre si sovrappongono la finestra nella parte inferiore dello z-order.</span><span class="sxs-lookup"><span data-stu-id="1385a-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1385a-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="1385a-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1385a-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="1385a-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1385a-110">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="1385a-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="1385a-111">Per i controlli dei livelli in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="1385a-111">To layer controls at design time</span></span>  
  
1.  <span data-ttu-id="1385a-112">Selezionare un controllo che si desidera di livello.</span><span class="sxs-lookup"><span data-stu-id="1385a-112">Select a control that you want to layer.</span></span>  
  
2.  <span data-ttu-id="1385a-113">Nel **formato** dal menu **ordine**, quindi fare clic su **porta in primo piano** o **porta in secondo piano**.</span><span class="sxs-lookup"><span data-stu-id="1385a-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="1385a-114">Per i controlli dei livelli a livello di codice</span><span class="sxs-lookup"><span data-stu-id="1385a-114">To layer controls programmatically</span></span>  
  
-   <span data-ttu-id="1385a-115">Usare la <xref:System.Windows.Forms.Control.BringToFront%2A> e <xref:System.Windows.Forms.Control.SendToBack%2A> metodi per modificare l'ordine z dei controlli.</span><span class="sxs-lookup"><span data-stu-id="1385a-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="1385a-116">Ad esempio, se un <xref:System.Windows.Forms.TextBox> controllo `txtFirstName`, si trova di sotto di un altro controllo e si desidera venga in primo piano, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1385a-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="1385a-117">Supporta Windows Form *contenimento di controlli*.</span><span class="sxs-lookup"><span data-stu-id="1385a-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="1385a-118">Contenimento dei controlli prevede l'inserimento di un numero di controlli all'interno di un controllo contenitore, ad esempio un numero di <xref:System.Windows.Forms.RadioButton> controlli all'interno di un <xref:System.Windows.Forms.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="1385a-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="1385a-119">È quindi possibile livellare i controlli all'interno del controllo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="1385a-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="1385a-120">Spostando la casella di gruppo consente di spostare i controlli, perché sono contenuti all'interno.</span><span class="sxs-lookup"><span data-stu-id="1385a-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1385a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1385a-121">See Also</span></span>  
 [<span data-ttu-id="1385a-122">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="1385a-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="1385a-123">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1385a-123">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="1385a-124">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="1385a-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="1385a-125">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1385a-125">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="1385a-126">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="1385a-126">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
