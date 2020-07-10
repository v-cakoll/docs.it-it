---
title: Disporre gli oggetti su più livelli
description: Informazioni su come eseguire il livello di oggetti su controlli Windows Forms e form figlio per creare interfacce utente più complesse.
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6269b09c56963fefd500b9e1e6c9d7f51f9619cf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174510"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="80cbd-103">Procedura: eseguire il layer di oggetti su Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80cbd-103">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="80cbd-104">Quando si crea un'interfaccia utente complessa o si utilizza un form con interfaccia a documenti multipli (MDI), spesso si desidera eseguire il layer di entrambi i controlli e i form figlio per creare interfacce utente (UI) più complesse.</span><span class="sxs-lookup"><span data-stu-id="80cbd-104">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="80cbd-105">Per spostare e tenere traccia dei controlli e delle finestre all'interno del contesto di un gruppo, è possibile modificare l' *ordine z*.</span><span class="sxs-lookup"><span data-stu-id="80cbd-105">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="80cbd-106">L'ordine z è il livello visivo dei controlli in un form lungo l'asse z del form (profondità).</span><span class="sxs-lookup"><span data-stu-id="80cbd-106">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="80cbd-107">La finestra nella parte superiore dello z-order si sovrappone a tutte le altre finestre.</span><span class="sxs-lookup"><span data-stu-id="80cbd-107">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="80cbd-108">Tutte le altre finestre si sovrappongono alla finestra nella parte inferiore dello z-order.</span><span class="sxs-lookup"><span data-stu-id="80cbd-108">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="80cbd-109">Per eseguire il livello di controlli in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="80cbd-109">To layer controls at design time</span></span>

1. <span data-ttu-id="80cbd-110">In Visual Studio selezionare un controllo che si desidera applicare al livello.</span><span class="sxs-lookup"><span data-stu-id="80cbd-110">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="80cbd-111">Scegliere **Order**dal menu **Format** , quindi selezionare **Bring to front** o **Send to back**.</span><span class="sxs-lookup"><span data-stu-id="80cbd-111">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="80cbd-112">Per livelli di controlli a livello di codice</span><span class="sxs-lookup"><span data-stu-id="80cbd-112">To layer controls programmatically</span></span>

<span data-ttu-id="80cbd-113">Usare i <xref:System.Windows.Forms.Control.BringToFront%2A> <xref:System.Windows.Forms.Control.SendToBack%2A> metodi e per modificare l'ordine z dei controlli.</span><span class="sxs-lookup"><span data-stu-id="80cbd-113">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="80cbd-114">Se, ad esempio, un <xref:System.Windows.Forms.TextBox> controllo, `txtFirstName` , è sotto un altro controllo e si desidera utilizzarlo in primo piano, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="80cbd-114">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

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
> <span data-ttu-id="80cbd-115">Windows Forms supporta il *contenimento del controllo*.</span><span class="sxs-lookup"><span data-stu-id="80cbd-115">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="80cbd-116">Il contenimento dei controlli comporta l'inserimento di un numero di controlli all'interno di un controllo contenitore, ad esempio un numero di <xref:System.Windows.Forms.RadioButton> controlli all'interno di un <xref:System.Windows.Forms.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="80cbd-116">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="80cbd-117">È quindi possibile sovrapporre i controlli all'interno del controllo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="80cbd-117">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="80cbd-118">Spostando la casella di gruppo si spostano anche i controlli, perché sono contenuti al suo interno.</span><span class="sxs-lookup"><span data-stu-id="80cbd-118">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="80cbd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80cbd-119">See also</span></span>

- [<span data-ttu-id="80cbd-120">Controlli di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80cbd-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="80cbd-121">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="80cbd-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="80cbd-122">Controlli da utilizzare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="80cbd-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="80cbd-123">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="80cbd-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
