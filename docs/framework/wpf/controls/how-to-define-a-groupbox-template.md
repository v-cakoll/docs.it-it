---
title: 'Procedura: Definire un modello GroupBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 6b4ad4a588aab93f5445cda962af890bfcd41c14
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377664"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="21d0e-102">Procedura: Definire un modello GroupBox</span><span class="sxs-lookup"><span data-stu-id="21d0e-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="21d0e-103">Questo esempio viene illustrato come creare un modello per un <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="21d0e-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21d0e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="21d0e-104">Example</span></span>  
 <span data-ttu-id="21d0e-105">L'esempio seguente definisce una <xref:System.Windows.Controls.GroupBox> modello di controllo utilizzando un <xref:System.Windows.Controls.Grid> controllo per il layout.</span><span class="sxs-lookup"><span data-stu-id="21d0e-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="21d0e-106">Il modello Usa un <xref:System.Windows.Controls.BorderGapMaskConverter> per definire il bordo del <xref:System.Windows.Controls.GroupBox> in modo che non nasconda la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenuto.</span><span class="sxs-lookup"><span data-stu-id="21d0e-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="21d0e-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21d0e-107">See also</span></span>
- <xref:System.Windows.Controls.GroupBox>
- <span data-ttu-id="21d0e-108">[Procedura: Creare un controllo GroupBox](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="21d0e-108">[How to: Create a GroupBox](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span></span>
