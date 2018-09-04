---
title: 'Procedura: impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 7f698a517fbf72ceafde4a117b4d92dd9d352834
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43540562"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="baef1-102">Procedura: impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="baef1-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="baef1-103">È possibile impostare un <xref:System.Windows.Forms.ToolTip> stringa nel codice o nella finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="baef1-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="baef1-104">Per altre informazioni sul <xref:System.Windows.Forms.ToolTip> componente, vedere [Cenni preliminari sul componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="baef1-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baef1-105">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="baef1-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="baef1-106">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="baef1-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="baef1-107">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="baef1-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="baef1-108">Per impostare una descrizione comandi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="baef1-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="baef1-109">Aggiungere il controllo che verrà visualizzata la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="baef1-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="baef1-110">Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo di <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="baef1-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
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
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="baef1-111">Per impostare una descrizione comando nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="baef1-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="baef1-112">Aggiungere un componente <xref:System.Windows.Forms.ToolTip> al form.</span><span class="sxs-lookup"><span data-stu-id="baef1-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="baef1-113">Selezionare il controllo che consente di visualizzare la descrizione comando o aggiungerlo al form.</span><span class="sxs-lookup"><span data-stu-id="baef1-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="baef1-114">Nel **proprietà** impostare nella finestra di **descrizione comando su ToolTip1** valore da una stringa di testo appropriata.</span><span class="sxs-lookup"><span data-stu-id="baef1-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baef1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baef1-115">See Also</span></span>  
 [<span data-ttu-id="baef1-116">Panoramica sul componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="baef1-116">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="baef1-117">Procedura: Modifica del ritardo del componente ToolTip di Windows Form</span><span class="sxs-lookup"><span data-stu-id="baef1-117">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [<span data-ttu-id="baef1-118">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="baef1-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
