---
title: 'Procedura: modificare i bordi di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: e04234b4f2f18738567c3f9846d8ae0c94780fcb
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44193185"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="e47ba-102">Procedura: modificare i bordi di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e47ba-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="e47ba-103">Quando si stabiliscono l'aspetto e il comportamento di Windows Form, è possibile scegliere tra diversi stili bordo.</span><span class="sxs-lookup"><span data-stu-id="e47ba-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="e47ba-104">Modificando la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A>, è possibile controllare il comportamento di ridimensionamento del form.</span><span class="sxs-lookup"><span data-stu-id="e47ba-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="e47ba-105">Inoltre, l'impostazione di <xref:System.Windows.Forms.Form.FormBorderStyle%2A> influisce sul modo in cui la barra del titolo viene visualizzata e su quali pulsanti possono apparire sulla barra stessa.</span><span class="sxs-lookup"><span data-stu-id="e47ba-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="e47ba-106">Per altre informazioni, vedere <xref:System.Windows.Forms.FormBorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="e47ba-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="e47ba-107">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="e47ba-107">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="e47ba-108">Vedere anche [procedura: modificare i bordi di Windows Form usando la finestra di progettazione](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="e47ba-108">See also [How to: Change the Borders of Windows Forms Using the Designer](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="e47ba-109">Per impostare lo stile bordo di Windows Form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="e47ba-109">To set the border style of Windows Forms programmatically</span></span>  
  
-   <span data-ttu-id="e47ba-110">Impostare la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A> sullo stile desiderato.</span><span class="sxs-lookup"><span data-stu-id="e47ba-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="e47ba-111">Esempio di codice seguente imposta lo stile del bordo del form `DlgBx1` a <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span><span class="sxs-lookup"><span data-stu-id="e47ba-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     <span data-ttu-id="e47ba-112">Vedere anche [procedura: creare finestre di dialogo in fase di progettazione](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="e47ba-112">Also see [How to: Create Dialog Boxes at Design Time](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span></span>  
  
     <span data-ttu-id="e47ba-113">Inoltre, se si è scelto un stile del bordo per il modulo che fornisce facoltativo **Riduci a icona** e **Ingrandisci** pulsanti, è possibile specificare se si desidera che uno o entrambi i pulsanti debbano essere funzionali.</span><span class="sxs-lookup"><span data-stu-id="e47ba-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="e47ba-114">Questi pulsanti sono utili quando si desidera controllare da vicino l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="e47ba-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="e47ba-115">Il **Riduci a icona** e **Ingrandisci** pulsanti sono abilitati per impostazione predefinita e le relative funzionalità viene modificato tramite il **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="e47ba-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47ba-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e47ba-116">See Also</span></span>  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [<span data-ttu-id="e47ba-117">Guida introduttiva a Windows Form</span><span class="sxs-lookup"><span data-stu-id="e47ba-117">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
