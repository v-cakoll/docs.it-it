---
title: 'Procedura: Creare un modulo con interfaccia a documenti multipli con unione di menu e controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 0edcc27968c55908cda0e881ed66f83323316711
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591312"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="7a354-102">Procedura: Creare un modulo con interfaccia a documenti multipli con unione di menu e controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7a354-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="7a354-103">Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu.</span><span class="sxs-lookup"><span data-stu-id="7a354-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="7a354-104">I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="7a354-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="7a354-105">È disponibile supporto completo per questa funzionalità in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7a354-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="7a354-106">Vedere anche [procedura dettagliata: Creazione di un Form MDI con unione di Menu e controlli ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7a354-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a354-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a354-107">Example</span></span>  
 <span data-ttu-id="7a354-108">L'esempio di codice seguente illustra come usare i controlli <xref:System.Windows.Forms.ToolStripPanel> con un form MDI.</span><span class="sxs-lookup"><span data-stu-id="7a354-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="7a354-109">Il form supporta anche l'unione dei menu con menu figlio.</span><span class="sxs-lookup"><span data-stu-id="7a354-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7a354-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7a354-110">Compiling the Code</span></span>  
 <span data-ttu-id="7a354-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a354-111">This code example requires:</span></span>  
  
- <span data-ttu-id="7a354-112">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="7a354-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a354-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a354-113">See also</span></span>

- [<span data-ttu-id="7a354-114">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7a354-114">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
