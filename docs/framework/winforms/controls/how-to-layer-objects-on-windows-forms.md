---
title: 'Procedura: Disporre oggetti su più livelli in Windows Forms'
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
ms.openlocfilehash: 80973e16445079876e01c89f20b5ecbdca602eb8
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039716"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="6ec3b-102">Procedura: Disporre oggetti su più livelli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ec3b-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="6ec3b-103">Quando si crea un'interfaccia utente complessa o si utilizza un form con interfaccia a documenti multipli (MDI), spesso si desidera eseguire il layer di entrambi i controlli e i form figlio per creare interfacce utente (UI) più complesse.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="6ec3b-104">Per spostare e tenere traccia dei controlli e delle finestre all'interno del contesto di un gruppo, è possibile modificare l'ordine z.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="6ec3b-105">L' *ordine z* è il livello visivo dei controlli in un form lungo l'asse z del form (profondità).</span><span class="sxs-lookup"><span data-stu-id="6ec3b-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="6ec3b-106">La finestra nella parte superiore dello z-order si sovrappone a tutte le altre finestre.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="6ec3b-107">Tutte le altre finestre si sovrappongono alla finestra nella parte inferiore dello z-order.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-107">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="6ec3b-108">Per eseguire il livello di controlli in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="6ec3b-108">To layer controls at design time</span></span>

1. <span data-ttu-id="6ec3b-109">Selezionare un controllo che si desidera applicare al livello.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-109">Select a control that you want to layer.</span></span>

2. <span data-ttu-id="6ec3b-110">Scegliere **Ordina**dal menu **formato** , quindi fare clic su **porta in primo piano** o su **Invia a indietro**.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-110">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="6ec3b-111">Per livelli di controlli a livello di codice</span><span class="sxs-lookup"><span data-stu-id="6ec3b-111">To layer controls programmatically</span></span>

- <span data-ttu-id="6ec3b-112">Usare i <xref:System.Windows.Forms.Control.BringToFront%2A> metodi <xref:System.Windows.Forms.Control.SendToBack%2A> e per modificare l'ordine z dei controlli.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-112">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

     <span data-ttu-id="6ec3b-113">Se, ad esempio, <xref:System.Windows.Forms.TextBox> un controllo `txtFirstName`,, è sotto un altro controllo e si desidera utilizzarlo in primo piano, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6ec3b-113">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

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
>  <span data-ttu-id="6ec3b-114">Windows Forms supporta il contenimento del *controllo*.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-114">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="6ec3b-115">Il contenimento dei controlli comporta l'inserimento di un numero di controlli all'interno di un controllo contenitore <xref:System.Windows.Forms.RadioButton> , ad esempio <xref:System.Windows.Forms.GroupBox> un numero di controlli all'interno di un controllo.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-115">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="6ec3b-116">È quindi possibile sovrapporre i controlli all'interno del controllo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-116">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="6ec3b-117">Spostando la casella di gruppo si spostano anche i controlli, perché sono contenuti al suo interno.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-117">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ec3b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ec3b-118">See also</span></span>

- [<span data-ttu-id="6ec3b-119">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6ec3b-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="6ec3b-120">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6ec3b-120">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="6ec3b-121">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="6ec3b-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="6ec3b-122">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6ec3b-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="6ec3b-123">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="6ec3b-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
