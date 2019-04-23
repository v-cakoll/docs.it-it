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
ms.openlocfilehash: 066ccc649105018d20cb86b6e576a1a238e0dc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973266"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="b5d26-102">Procedura: Applicare la correzione gamma a una sfumatura</span><span class="sxs-lookup"><span data-stu-id="b5d26-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="b5d26-103">È possibile abilitare la correzione gamma per un pennello sfumato lineare impostando la proprietà del pennello <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="b5d26-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="b5d26-104">È possibile disabilitare la correzione gamma impostando il <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="b5d26-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="b5d26-105">La correzione gamma è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5d26-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5d26-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5d26-106">Example</span></span>  

<span data-ttu-id="b5d26-107">Nell'esempio seguente è un metodo che viene chiamato da un controllo <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b5d26-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b5d26-108">L'esempio crea un pennello sfumato lineare e tale utilizzato per riempire i due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="b5d26-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="b5d26-109">Il primo rettangolo viene riempito senza la correzione gamma e il secondo rettangolo viene riempito con la correzione gamma.</span><span class="sxs-lookup"><span data-stu-id="b5d26-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="b5d26-110">La figura seguente mostra i due rettangoli colorati.</span><span class="sxs-lookup"><span data-stu-id="b5d26-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="b5d26-111">Il rettangolo superiore che non dispone di correzione gamma, viene visualizzato scuro al centro.</span><span class="sxs-lookup"><span data-stu-id="b5d26-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="b5d26-112">Il rettangolo nella parte inferiore che include la correzione gamma, sembra avere ulteriori intensità uniforme.</span><span class="sxs-lookup"><span data-stu-id="b5d26-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="b5d26-113">![Sfumatura](./media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="b5d26-113">![Gradient](./media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b5d26-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b5d26-114">Compiling the Code</span></span>  
 <span data-ttu-id="b5d26-115">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b5d26-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d26-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5d26-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="b5d26-117">Uso di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="b5d26-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
