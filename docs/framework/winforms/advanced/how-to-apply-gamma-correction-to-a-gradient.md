---
title: 'Procedura: applicare la correzione gamma a una sfumatura'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2721a45381f2d0befe82d6d0db2630f3eae08d51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="9a465-102">Procedura: applicare la correzione gamma a una sfumatura</span><span class="sxs-lookup"><span data-stu-id="9a465-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="9a465-103">È possibile abilitare la correzione gamma per una sfumatura lineare impostando il pennello <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="9a465-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="9a465-104">È possibile disabilitare la correzione gamma impostando il <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="9a465-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="9a465-105">La correzione gamma è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9a465-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a465-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a465-106">Example</span></span>  
 <span data-ttu-id="9a465-107">L'esempio crea un pennello sfumato lineare e tale utilizzato per riempire due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="9a465-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="9a465-108">Il primo rettangolo viene riempito senza correzione gamma e il secondo rettangolo viene riempito con la correzione gamma.</span><span class="sxs-lookup"><span data-stu-id="9a465-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="9a465-109">Nella figura seguente mostra i due rettangoli riempiti.</span><span class="sxs-lookup"><span data-stu-id="9a465-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="9a465-110">Il rettangolo superiore, che non dispone di correzione gamma, è nero al centro.</span><span class="sxs-lookup"><span data-stu-id="9a465-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="9a465-111">Il rettangolo inferiore, che include la correzione gamma, viene visualizzato con intensità maggiormente uniforme.</span><span class="sxs-lookup"><span data-stu-id="9a465-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="9a465-112">![Sfumatura](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="9a465-112">![Gradient](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a465-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9a465-113">Compiling the Code</span></span>  
 <span data-ttu-id="9a465-114">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="9a465-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a465-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a465-115">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>  
 [<span data-ttu-id="9a465-116">Uso di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="9a465-116">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
