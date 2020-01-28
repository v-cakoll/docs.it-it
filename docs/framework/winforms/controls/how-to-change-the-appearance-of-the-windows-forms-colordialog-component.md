---
title: Modificare l'aspetto del componente ColorDialog
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
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746643"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="bbea7-102">Procedura: modificare l'aspetto del componente ColorDialog di Windows Form</span><span class="sxs-lookup"><span data-stu-id="bbea7-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="bbea7-103">È possibile configurare l'aspetto del componente Windows Forms <xref:System.Windows.Forms.ColorDialog> con una serie di proprietà.</span><span class="sxs-lookup"><span data-stu-id="bbea7-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="bbea7-104">La finestra di dialogo include due sezioni, una che mostra i colori di base e l'altra che consente all'utente di definire colori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="bbea7-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="bbea7-105">La maggior parte delle proprietà consente di limitare i colori selezionabili dall'utente dalla finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="bbea7-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="bbea7-106">Se la proprietà <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> è impostata su `true`, l'utente può definire colori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="bbea7-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="bbea7-107">La proprietà <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> viene `true` se la finestra di dialogo è espansa per definire colori personalizzati; in caso contrario, l'utente deve fare clic sul pulsante "Definisci colori personalizzati".</span><span class="sxs-lookup"><span data-stu-id="bbea7-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="bbea7-108">Quando la proprietà <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> è impostata su `true`, nella finestra di dialogo vengono visualizzati tutti i colori disponibili nel set di colori di base.</span><span class="sxs-lookup"><span data-stu-id="bbea7-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="bbea7-109">Se la proprietà <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> è impostata su `true`, l'utente non è in grado di selezionare i colori dimessi; per la selezione sono disponibili solo colori a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="bbea7-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="bbea7-110">Se la proprietà <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> è impostata su `true`, nella finestra di dialogo viene visualizzato un pulsante?.</span><span class="sxs-lookup"><span data-stu-id="bbea7-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="bbea7-111">Quando l'utente fa clic sul pulsante?, viene generato l'evento <xref:System.Windows.Forms.CommonDialog.HelpRequest> del componente <xref:System.Windows.Forms.ColorDialog>.</span><span class="sxs-lookup"><span data-stu-id="bbea7-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="bbea7-112">Per configurare l'aspetto della finestra di dialogo colore</span><span class="sxs-lookup"><span data-stu-id="bbea7-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="bbea7-113">Impostare le proprietà <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>e <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> sui valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="bbea7-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bbea7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbea7-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="bbea7-115">Componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="bbea7-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="bbea7-116">Cenni preliminari sul componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="bbea7-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
