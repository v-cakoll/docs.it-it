---
title: 'Procedura: Usare una classe di rendering del controllo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: 7115c227cb24cf12a50073d0dc587524abf0cbb9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163576"
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="e1eec-102">Procedura: Usare una classe di rendering del controllo</span><span class="sxs-lookup"><span data-stu-id="e1eec-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="e1eec-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Forms.ComboBoxRenderer> classe per il rendering di controllo di finestra la freccia a discesa di una casella combinata.</span><span class="sxs-lookup"><span data-stu-id="e1eec-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="e1eec-104">L'esempio è costituito il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo di un controllo personalizzato semplice.</span><span class="sxs-lookup"><span data-stu-id="e1eec-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="e1eec-105">Il <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> proprietà viene utilizzata per determinare se gli stili di visualizzazione sono abilitati nell'area client delle finestre dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1eec-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="e1eec-106">Se gli stili visivi sono attivi, il <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> metodo verrà eseguito il rendering la freccia a discesa con stili di visualizzazione; in caso contrario, il <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> metodo verrà eseguito il rendering sulla freccia giù nello stile classico di Windows.</span><span class="sxs-lookup"><span data-stu-id="e1eec-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1eec-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1eec-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1eec-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e1eec-108">Compiling the Code</span></span>  
 <span data-ttu-id="e1eec-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1eec-109">This example requires:</span></span>  
  
-   <span data-ttu-id="e1eec-110">Un controllo personalizzato derivato dal <xref:System.Windows.Forms.Control> classe.</span><span class="sxs-lookup"><span data-stu-id="e1eec-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="e1eec-111">Oggetto <xref:System.Windows.Forms.Form> che ospita il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e1eec-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="e1eec-112">Fa riferimento per la <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, e <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e1eec-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1eec-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1eec-113">See also</span></span>

- [<span data-ttu-id="e1eec-114">Rendering dei controlli con stili visivi</span><span class="sxs-lookup"><span data-stu-id="e1eec-114">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
