---
title: 'Procedura: Definire un modello GroupBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: dd53af87ec2d12b2ed0dcf2b23374d76e8f631a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225716"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="bbc9a-102">Procedura: Definire un modello GroupBox</span><span class="sxs-lookup"><span data-stu-id="bbc9a-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="bbc9a-103">Questo esempio viene illustrato come creare un modello per un <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="bbc9a-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbc9a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbc9a-104">Example</span></span>  
 <span data-ttu-id="bbc9a-105">L'esempio seguente definisce una <xref:System.Windows.Controls.GroupBox> modello di controllo utilizzando un <xref:System.Windows.Controls.Grid> controllo per il layout.</span><span class="sxs-lookup"><span data-stu-id="bbc9a-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="bbc9a-106">Il modello Usa un <xref:System.Windows.Controls.BorderGapMaskConverter> per definire il bordo del <xref:System.Windows.Controls.GroupBox> in modo che non nasconda la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenuto.</span><span class="sxs-lookup"><span data-stu-id="bbc9a-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="bbc9a-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbc9a-107">See also</span></span>

- <xref:System.Windows.Controls.GroupBox>
- [<span data-ttu-id="bbc9a-108">Procedura: Creare un controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="bbc9a-108">How to: Create a GroupBox</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))
