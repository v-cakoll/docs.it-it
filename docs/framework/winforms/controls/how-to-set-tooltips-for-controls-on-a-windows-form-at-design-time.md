---
title: 'Procedura: impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione'
description: Informazioni su come impostare le descrizioni comandi per i controlli a livello o nel Progettazione Windows Form in Visual Studio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 15134b38d11de30d0e6a2f998f6ea266affc40d7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325979"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="fbd75-103">Procedura: impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="fbd75-103">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="fbd75-104">È possibile impostare una <xref:System.Windows.Forms.ToolTip> stringa nel codice o nell'progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fbd75-104">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="fbd75-105">Per ulteriori informazioni sul <xref:System.Windows.Forms.ToolTip> componente, vedere [Cenni preliminari sul componente ToolTip](tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="fbd75-105">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="fbd75-106">Impostare una descrizione comando a livello di codice</span><span class="sxs-lookup"><span data-stu-id="fbd75-106">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="fbd75-107">Aggiungere il controllo in cui viene visualizzata la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="fbd75-107">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="fbd75-108">Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo del <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="fbd75-108">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="fbd75-109">Impostare una descrizione comando nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="fbd75-109">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="fbd75-110">In Visual Studio aggiungere un <xref:System.Windows.Forms.ToolTip> componente al modulo.</span><span class="sxs-lookup"><span data-stu-id="fbd75-110">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="fbd75-111">Consente di selezionare il controllo per la visualizzazione della descrizione comando oppure di aggiungerlo al form.</span><span class="sxs-lookup"><span data-stu-id="fbd75-111">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="fbd75-112">Nella finestra **Proprietà** impostare la **Descrizione comando sul valore ToolTip1 su** una stringa di testo appropriata.</span><span class="sxs-lookup"><span data-stu-id="fbd75-112">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="fbd75-113">Per rimuovere una descrizione comando a livello di codice</span><span class="sxs-lookup"><span data-stu-id="fbd75-113">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="fbd75-114">Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo del <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="fbd75-114">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="fbd75-115">Rimuovere una descrizione comando nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="fbd75-115">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="fbd75-116">In Visual Studio selezionare il controllo che visualizza la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="fbd75-116">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="fbd75-117">Nella finestra **Proprietà** eliminare il testo nella **Descrizione comando in ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="fbd75-117">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbd75-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fbd75-118">See also</span></span>

- [<span data-ttu-id="fbd75-119">Cenni preliminari sul componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="fbd75-119">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="fbd75-120">Procedura: modificare il ritardo del componente ToolTip di Windows Form</span><span class="sxs-lookup"><span data-stu-id="fbd75-120">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="fbd75-121">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="fbd75-121">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
