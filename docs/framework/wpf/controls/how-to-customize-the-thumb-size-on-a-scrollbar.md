---
title: 'Procedura: Personalizzare le dimensioni del cursore in una barra di scorrimento'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207279"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>Procedura: Personalizzare le dimensioni del cursore in una barra di scorrimento
In questo argomento illustra come impostare il <xref:System.Windows.Controls.Primitives.Thumb> di un <xref:System.Windows.Controls.Primitives.ScrollBar> a una dimensione fissa e su come specificare una dimensione minima per il <xref:System.Windows.Controls.Primitives.Thumb> di un <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
 L'esempio seguente crea una <xref:System.Windows.Controls.Primitives.ScrollBar> che ha un <xref:System.Windows.Controls.Primitives.Thumb> con una dimensione fissa. Nell'esempio viene impostata la <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> proprietà del <xref:System.Windows.Controls.Primitives.Thumb> al <xref:System.Double.NaN> e imposta l'altezza del <xref:System.Windows.Controls.Primitives.Thumb>.  Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> che ha una larghezza fissa, impostare la larghezza del <xref:System.Windows.Controls.Primitives.Thumb>.  
  
## <a name="code"></a>Codice  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>Descrizione  
 L'esempio seguente crea una <xref:System.Windows.Controls.Primitives.ScrollBar> che ha un <xref:System.Windows.Controls.Primitives.Thumb> con una dimensione minima. L'esempio imposta il valore di <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>. Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> una larghezza minima, impostare il <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.  
  
## <a name="code"></a>Codice  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Stili e modelli di ScrollBar](scrollbar-styles-and-templates.md)
