---
title: 'Procedura: Trovare elementi generati da un oggetto ControlTemplate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 9a6609d70a6b863f16533aac81ffce4daf171bcf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364502"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Procedura: Trovare elementi generati da un oggetto ControlTemplate
Questo esempio illustra come trovare gli elementi che vengono generati da un <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra uno stile che viene creata una semplice <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Button> classe:  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Per trovare un elemento all'interno del modello viene applicato il modello, è possibile chiamare il <xref:System.Windows.FrameworkTemplate.FindName%2A> metodo di <xref:System.Windows.Controls.Control.Template%2A>. L'esempio seguente crea una finestra di messaggio che mostra il valore di larghezza effettiva dei <xref:System.Windows.Controls.Grid> all'interno del modello di controllo:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: trovare elementi generati da un oggetto DataTemplate](../data/how-to-find-datatemplate-generated-elements.md)
- [Applicazione di stili e modelli](styling-and-templating.md)
- [Ambiti dei nomi XAML WPF](../advanced/wpf-xaml-namescopes.md)
- [Strutture ad albero in WPF](../advanced/trees-in-wpf.md)
