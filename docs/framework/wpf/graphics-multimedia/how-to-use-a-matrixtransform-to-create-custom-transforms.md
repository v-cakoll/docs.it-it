---
title: 'Procedura: utilizzare un MatrixTransform per creare trasformazioni personalizzate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1414ae590be10c3adcc6857492e23bf659beec67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="b7263-102">Procedura: utilizzare un MatrixTransform per creare trasformazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b7263-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="b7263-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.MatrixTransform> a quale traslare (spostare) la posizione dell'estensione e l'inclinazione di una <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="b7263-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7263-104">Utilizzare il <xref:System.Windows.Media.MatrixTransform> classe per creare trasformazioni personalizzate non disponibili per il <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, o <xref:System.Windows.Media.TranslateTransform> classi.</span><span class="sxs-lookup"><span data-stu-id="b7263-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7263-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7263-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="b7263-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7263-106">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform>  
 <xref:System.Windows.Media.Transform>  
 [<span data-ttu-id="b7263-107">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="b7263-107">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="b7263-108">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b7263-108">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [<span data-ttu-id="b7263-109">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="b7263-109">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
