---
title: "Procedura: disporre oggetti su più livelli in Windows Form"
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
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f042816b912a0de643dd1d0f66ddba6d5eff7df2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="10127-102">Procedura: disporre oggetti su più livelli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="10127-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="10127-103">Quando si crea un'interfaccia utente complessi o di lavoro con un form MDI (interfaccia), spesso si desidera sia form e controlli figlio per creare complesse interfacce utente (UI) di livello.</span><span class="sxs-lookup"><span data-stu-id="10127-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="10127-104">Per spostare e tenere traccia di controlli e finestre all'interno del contesto di un gruppo, modificare l'ordine z.</span><span class="sxs-lookup"><span data-stu-id="10127-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="10127-105">*Ordine Z* è disposizione visiva di controlli in un form lungo l'asse z del form (profondità).</span><span class="sxs-lookup"><span data-stu-id="10127-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="10127-106">La finestra nella parte superiore dello z-order si sovrappone a tutte le altre finestre.</span><span class="sxs-lookup"><span data-stu-id="10127-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="10127-107">Tutte le altre finestre si sovrappongono finestra nella parte inferiore dello z-order.</span><span class="sxs-lookup"><span data-stu-id="10127-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10127-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="10127-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="10127-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="10127-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="10127-110">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="10127-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="10127-111">Per i controlli dei livelli in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="10127-111">To layer controls at design time</span></span>  
  
1.  <span data-ttu-id="10127-112">Selezionare un controllo che si desidera di livello.</span><span class="sxs-lookup"><span data-stu-id="10127-112">Select a control that you want to layer.</span></span>  
  
2.  <span data-ttu-id="10127-113">Nel **formato** dal menu **ordine**, quindi fare clic su **porta in primo piano** o **porta in secondo piano**.</span><span class="sxs-lookup"><span data-stu-id="10127-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="10127-114">A livello di controlli a livello di codice</span><span class="sxs-lookup"><span data-stu-id="10127-114">To layer controls programmatically</span></span>  
  
-   <span data-ttu-id="10127-115">Utilizzare il <xref:System.Windows.Forms.Control.BringToFront%2A> e <xref:System.Windows.Forms.Control.SendToBack%2A> metodi per modificare l'ordine z dei controlli.</span><span class="sxs-lookup"><span data-stu-id="10127-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="10127-116">Ad esempio, se un <xref:System.Windows.Forms.TextBox> controllo `txtFirstName`, si trova di sotto di un altro controllo e si desidera in primo piano, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="10127-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
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
>  <span data-ttu-id="10127-117">Windows Form supporta *contenimento di controlli*.</span><span class="sxs-lookup"><span data-stu-id="10127-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="10127-118">Che prevede l'inserimento di più controlli all'interno di un controllo, ad esempio un numero di <xref:System.Windows.Forms.RadioButton> controlli all'interno di un <xref:System.Windows.Forms.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="10127-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="10127-119">È quindi possibile creare livelli i controlli all'interno del controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="10127-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="10127-120">Spostando la casella di gruppo consente di spostare i controlli, perché sono contenuti all'interno.</span><span class="sxs-lookup"><span data-stu-id="10127-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10127-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10127-121">See Also</span></span>  
 [<span data-ttu-id="10127-122">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="10127-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="10127-123">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="10127-123">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="10127-124">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="10127-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="10127-125">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="10127-125">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="10127-126">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="10127-126">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
