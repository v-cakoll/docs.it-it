---
title: 'Procedura: definire un modello GroupBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: ed66d51e87a25f74e646d0d535ac9e4ee9c8a056
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551136"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="d0add-102">Procedura: definire un modello GroupBox</span><span class="sxs-lookup"><span data-stu-id="d0add-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="d0add-103">In questo esempio viene illustrato come creare un modello per un <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="d0add-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0add-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0add-104">Example</span></span>  
 <span data-ttu-id="d0add-105">L'esempio seguente definisce un <xref:System.Windows.Controls.GroupBox> il modello di controllo utilizzando un <xref:System.Windows.Controls.Grid> controllo per il layout.</span><span class="sxs-lookup"><span data-stu-id="d0add-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="d0add-106">Il modello utilizza un <xref:System.Windows.Controls.BorderGapMaskConverter> per definire il bordo del <xref:System.Windows.Controls.GroupBox> in modo che non nasconda la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenuto.</span><span class="sxs-lookup"><span data-stu-id="d0add-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="d0add-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0add-107">See Also</span></span>  
 <xref:System.Windows.Controls.GroupBox>  
 [<span data-ttu-id="d0add-108">Procedure relative al controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="d0add-108">GroupBox How-to Topics</span></span>](http://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
