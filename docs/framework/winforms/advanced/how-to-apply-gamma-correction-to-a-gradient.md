---
title: 'Procedura: Applicare la correzione gamma a una sfumatura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2019
ms.locfileid: "63809470"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="6de27-102">Procedura: Applicare la correzione gamma a una sfumatura</span><span class="sxs-lookup"><span data-stu-id="6de27-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="6de27-103">È possibile abilitare la correzione gamma per un pennello sfumato lineare impostando la proprietà del pennello <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="6de27-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="6de27-104">È possibile disabilitare la correzione gamma impostando il <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="6de27-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="6de27-105">La correzione gamma è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6de27-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6de27-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="6de27-106">Example</span></span>  

<span data-ttu-id="6de27-107">Nell'esempio seguente è un metodo che viene chiamato da un controllo <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6de27-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="6de27-108">L'esempio crea un pennello sfumato lineare e tale utilizzato per riempire i due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="6de27-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="6de27-109">Il primo rettangolo viene riempito senza la correzione gamma e il secondo rettangolo viene riempito con la correzione gamma.</span><span class="sxs-lookup"><span data-stu-id="6de27-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="6de27-110">La figura seguente mostra i due rettangoli colorati.</span><span class="sxs-lookup"><span data-stu-id="6de27-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="6de27-111">Il rettangolo superiore che non dispone di correzione gamma, viene visualizzato scuro al centro.</span><span class="sxs-lookup"><span data-stu-id="6de27-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="6de27-112">Il rettangolo nella parte inferiore che include la correzione gamma, sembra avere ulteriori intensità uniforme.</span><span class="sxs-lookup"><span data-stu-id="6de27-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 ![Due riempimento sfumatura rettangoli, con e senza la correzione gamma.](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6de27-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6de27-114">Compiling the Code</span></span>  
 <span data-ttu-id="6de27-115">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6de27-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de27-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6de27-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="6de27-117">Uso di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="6de27-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
