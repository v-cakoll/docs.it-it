---
title: "Procedura: Modificare l'aspetto del componente ColorDialog di Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: d2bb9e06d9d84a9b61c67510e9c012066f69d55e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329232"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="cbae9-102">Procedura: Modificare l'aspetto del componente ColorDialog di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbae9-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="cbae9-103">È possibile configurare l'aspetto delle forme Windows <xref:System.Windows.Forms.ColorDialog> componente con un numero di proprietà.</span><span class="sxs-lookup"><span data-stu-id="cbae9-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="cbae9-104">La finestra di dialogo include due sezioni, ovvero uno che mostra i colori di base e uno che consente all'utente di definire colori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="cbae9-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="cbae9-105">La maggior parte delle proprietà limitare colori selezionabili dall'utente nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cbae9-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="cbae9-106">Se il <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> è impostata su `true`, l'utente può definire colori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="cbae9-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="cbae9-107">Il <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> è di proprietà `true` se la finestra di dialogo viene espanso per definire colori personalizzati; in caso contrario, l'utente deve fare clic su un pulsante "Definisci colori personalizzati".</span><span class="sxs-lookup"><span data-stu-id="cbae9-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="cbae9-108">Quando la <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> è impostata su `true`, la finestra di dialogo consente di visualizzare tutti i colori disponibili nel set di colori di base.</span><span class="sxs-lookup"><span data-stu-id="cbae9-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="cbae9-109">Se il <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> è impostata su `true`, l'utente non è possibile selezionare i colori con dithering; sono possibile selezionare solo colori a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="cbae9-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="cbae9-110">Se il <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> è impostata su `true`, viene visualizzato un pulsante nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cbae9-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="cbae9-111">Quando l'utente fa clic sul pulsante della Guida, il <xref:System.Windows.Forms.ColorDialog> del componente <xref:System.Windows.Forms.CommonDialog.HelpRequest> viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="cbae9-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="cbae9-112">Per configurare l'aspetto della finestra di dialogo colore</span><span class="sxs-lookup"><span data-stu-id="cbae9-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="cbae9-113">Impostare il <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, e <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> proprietà sui valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="cbae9-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cbae9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbae9-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="cbae9-115">Componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="cbae9-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="cbae9-116">Cenni preliminari sul componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="cbae9-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
