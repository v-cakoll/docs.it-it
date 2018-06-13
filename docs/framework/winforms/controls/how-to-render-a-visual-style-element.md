---
title: 'Procedura: eseguire il rendering di un elemento dello stile visivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: 284fca2d3f2b8f47b60e4d9c639df4a6bd43c701
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537621"
---
# <a name="how-to-render-a-visual-style-element"></a><span data-ttu-id="667af-102">Procedura: eseguire il rendering di un elemento dello stile visivo</span><span class="sxs-lookup"><span data-stu-id="667af-102">How to: Render a Visual Style Element</span></span>
<span data-ttu-id="667af-103">Il <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> espone lo spazio dei nomi <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> elementi (UI) supportati dagli stili dell'interfaccia utente gli oggetti che rappresentano l'utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="667af-103">The <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespace exposes <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> objects that represent the Windows user interface (UI) elements supported by visual styles.</span></span> <span data-ttu-id="667af-104">In questo argomento viene illustrato come utilizzare il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> classe per eseguire il rendering di <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> che rappresenta il **Disconnetti** e **Arresta** pulsanti del menu Start.</span><span class="sxs-lookup"><span data-stu-id="667af-104">This topic demonstrates how to use the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> class to render the <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> that represents the **Log Off** and **Shut Down** buttons of the Start menu.</span></span>  
  
### <a name="to-render-a-visual-style-element"></a><span data-ttu-id="667af-105">Per eseguire il rendering di un elemento dello stile di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="667af-105">To render a visual style element</span></span>  
  
1.  <span data-ttu-id="667af-106">Creare un <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> e impostarla per l'elemento che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="667af-106">Create a <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> and set it to the element you want to draw.</span></span> <span data-ttu-id="667af-107">Si noti l'uso del <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> proprietà e <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> (metodo); il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> costruttore genera un'eccezione se gli stili di visualizzazione sono disabilitate o non è definito un elemento.</span><span class="sxs-lookup"><span data-stu-id="667af-107">Note the use of the <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> property and the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> method; the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> constructor will throw an exception if visual styles are disabled or an element is undefined.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  <span data-ttu-id="667af-108">Chiamare il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> metodo per il rendering dell'elemento che la <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> attualmente rappresenta.</span><span class="sxs-lookup"><span data-stu-id="667af-108">Call the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> method to render the element that the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> currently represents.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="667af-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="667af-109">Compiling the Code</span></span>  
 <span data-ttu-id="667af-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="667af-110">This example requires:</span></span>  
  
-   <span data-ttu-id="667af-111">Un controllo personalizzato derivato dalla <xref:System.Windows.Forms.Control> classe.</span><span class="sxs-lookup"><span data-stu-id="667af-111">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="667af-112">Oggetto <xref:System.Windows.Forms.Form> che ospita il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="667af-112">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="667af-113">I riferimenti al <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, e <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="667af-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="667af-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="667af-114">See Also</span></span>  
 [<span data-ttu-id="667af-115">Rendering dei controlli con stili visivi</span><span class="sxs-lookup"><span data-stu-id="667af-115">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
