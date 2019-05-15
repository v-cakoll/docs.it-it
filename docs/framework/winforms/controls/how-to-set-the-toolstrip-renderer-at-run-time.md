---
title: 'Procedura: Impostare il renderer ToolStrip in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
ms.openlocfilehash: 90a80ba421698a108cd7a358f89b64810b06efc9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591622"
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="e8447-102">Procedura: Impostare il renderer ToolStrip in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e8447-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="e8447-103">È possibile personalizzare l'aspetto del controllo <xref:System.Windows.Forms.ToolStrip> mediante la creazione di una classe `ProfessionalColorTable` personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e8447-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8447-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8447-104">Example</span></span>  
 <span data-ttu-id="e8447-105">L'esempio di codice seguente illustra come creare una classe `ProfessionalColorTable` personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e8447-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="e8447-106">Questa classe definisce le sfumature per un controllo <xref:System.Windows.Forms.MenuStrip> e un controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="e8447-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="e8447-107">Per usare questo esempio di codice, compilare ed eseguire l'applicazione, quindi scegliere **Change Colors** (Cambia colori) per applicare le sfumature definite nella classe personalizzata `ProfessionalColorTable`.</span><span class="sxs-lookup"><span data-stu-id="e8447-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="e8447-108">Definizione di una classe ProfessionalColorTable personalizzata</span><span class="sxs-lookup"><span data-stu-id="e8447-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="e8447-109">Le sfumature personalizzate sono definite nella classe `CustomProfessionalColors`.</span><span class="sxs-lookup"><span data-stu-id="e8447-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="e8447-110">Assegnazione di un renderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="e8447-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="e8447-111">Creare un nuovo oggetto `ToolStripProfessionalRenderer` con la classe `CustomProfessionalColors` e assegnarlo alla proprietà <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e8447-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e8447-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e8447-112">Compiling the Code</span></span>  
 <span data-ttu-id="e8447-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8447-113">This example requires:</span></span>  
  
- <span data-ttu-id="e8447-114">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e8447-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8447-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8447-115">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="e8447-116">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e8447-116">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
