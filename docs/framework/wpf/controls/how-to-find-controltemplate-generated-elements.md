---
title: 'Procedura: trovare elementi generati da un oggetto ControlTemplate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 232ee7d2859059591c9beff753f45781598a8127
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460714"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Procedura: trovare elementi generati da un oggetto ControlTemplate
Questo esempio illustra come trovare elementi generati da un <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato uno stile che crea una semplice <xref:System.Windows.Controls.ControlTemplate> per la classe <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Per trovare un elemento all'interno del modello dopo che è stato applicato il modello, è possibile chiamare il metodo <xref:System.Windows.FrameworkTemplate.FindName%2A> della <xref:System.Windows.Controls.Control.Template%2A>. Nell'esempio seguente viene creata una finestra di messaggio che mostra il valore di larghezza effettivo dell'<xref:System.Windows.Controls.Grid> all'interno del modello di controllo:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: trovare elementi generati da un oggetto DataTemplate](../data/how-to-find-datatemplate-generated-elements.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Ambiti dei nomi XAML WPF](../advanced/wpf-xaml-namescopes.md)
- [Strutture ad albero in WPF](../advanced/trees-in-wpf.md)
