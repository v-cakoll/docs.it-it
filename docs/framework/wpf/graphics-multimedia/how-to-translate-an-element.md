---
title: 'Procedura: convertire un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111972"
---
# <a name="how-to-translate-an-element"></a>Procedura: convertire un elemento
In questo esempio viene illustrato come convertire <xref:System.Windows.Media.TranslateTransform>(spostare) un elemento utilizzando un oggetto .  
  
 La <xref:System.Windows.Media.TranslateTransform> classe è particolarmente utile per spostare gli elementi all'interno di pannelli che non supportano il posizionamento assoluto. Ad esempio, applicando <xref:System.Windows.Media.TranslateTransform> a <xref:System.Windows.UIElement.RenderTransform%2A> alla proprietà di un elemento, è <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.DockPanel>possibile spostare un elemento all'interno di un oggetto o .  
  
 Utilizzare <xref:System.Windows.Media.TranslateTransform.X%2A> la proprietà <xref:System.Windows.Media.TranslateTransform> dell'oggetto per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse x. Utilizzare <xref:System.Windows.Media.TranslateTransform.Y%2A> la proprietà per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse y. Infine, applicare <xref:System.Windows.Media.TranslateTransform> l'oggetto alla <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.  
  
 L'esempio seguente <xref:System.Windows.Media.TranslateTransform> usa un oggetto per spostare un elemento di 50 pixel a destra e di 50 pixel verso il basso.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Per l'esempio completo, vedere Esempio di [trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
