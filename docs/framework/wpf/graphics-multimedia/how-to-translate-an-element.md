---
title: 'Procedura: convertire un elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 222aebe0ffe3d2bb1d84002a2ad94b0b92ede15b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-translate-an-element"></a>Procedura: convertire un elemento
In questo esempio viene illustrato come quale traslare (spostare) un elemento utilizzando un <xref:System.Windows.Media.TranslateTransform>.  
  
 La <xref:System.Windows.Media.TranslateTransform> classe è particolarmente utile per lo spostamento degli elementi all'interno di riquadri che non supportano il posizionamento assoluto. Ad esempio, applicando un <xref:System.Windows.Media.TranslateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un elemento, è possibile spostare un elemento all'interno di un <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel>.  
  
 Utilizzare il <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà del <xref:System.Windows.Media.TranslateTransform> per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse x. Utilizzare il <xref:System.Windows.Media.TranslateTransform.Y%2A> proprietà per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse y. Infine, applicare il <xref:System.Windows.Media.TranslateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.TranslateTransform> per spostare un pixel elemento 50 a destra e di 50 pixel in basso.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
