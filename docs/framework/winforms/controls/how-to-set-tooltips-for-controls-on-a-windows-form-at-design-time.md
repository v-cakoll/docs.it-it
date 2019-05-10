---
title: 'Procedura: Impostare le descrizioni comando per i controlli in un Windows Form in fase di progettazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211692"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="b2c02-102">Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="b2c02-102">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="b2c02-103">È possibile impostare un <xref:System.Windows.Forms.ToolTip> stringa nel codice o nella finestra di progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b2c02-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="b2c02-104">Per altre informazioni sul <xref:System.Windows.Forms.ToolTip> componente, vedere [Cenni preliminari sul componente ToolTip](tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b2c02-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="b2c02-105">Impostare una descrizione comandi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="b2c02-105">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="b2c02-106">Aggiungere il controllo che verrà visualizzata la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="b2c02-106">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="b2c02-107">Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo di <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="b2c02-107">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="b2c02-108">Impostare una descrizione comando nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="b2c02-108">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="b2c02-109">In Visual Studio, aggiungere un <xref:System.Windows.Forms.ToolTip> componente al form.</span><span class="sxs-lookup"><span data-stu-id="b2c02-109">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="b2c02-110">Selezionare il controllo che consente di visualizzare la descrizione comando o aggiungerlo al form.</span><span class="sxs-lookup"><span data-stu-id="b2c02-110">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="b2c02-111">Nel **proprietà** impostare nella finestra di **descrizione comando su ToolTip1** valore da una stringa di testo appropriata.</span><span class="sxs-lookup"><span data-stu-id="b2c02-111">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="b2c02-112">Per rimuovere una descrizione comandi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="b2c02-112">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="b2c02-113">Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo di <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="b2c02-113">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="b2c02-114">Rimuovere una descrizione comando nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="b2c02-114">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="b2c02-115">In Visual Studio, selezionare il controllo che visualizza la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="b2c02-115">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="b2c02-116">Nel **delle proprietà** finestra, eliminare il testo nel **descrizione comando su ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="b2c02-116">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2c02-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2c02-117">See also</span></span>

- [<span data-ttu-id="b2c02-118">Panoramica sul componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="b2c02-118">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="b2c02-119">Procedura: Modifica del ritardo del componente di descrizione comando di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2c02-119">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="b2c02-120">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="b2c02-120">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
