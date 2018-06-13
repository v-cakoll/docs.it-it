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
ms.openlocfilehash: 3d3032326a0cedc01b4a7ec8e6546044353d6b4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553910"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Procedura: trovare elementi generati da un oggetto ControlTemplate
In questo esempio viene illustrato come trovare gli elementi che vengono generati da un <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato uno stile che consente di creare una semplice <xref:System.Windows.Controls.ControlTemplate> per la <xref:System.Windows.Controls.Button> classe:  
  
 [!code-xaml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Per trovare un elemento all'interno del modello dopo che è stato applicato il modello, è possibile chiamare il <xref:System.Windows.FrameworkTemplate.FindName%2A> metodo il <xref:System.Windows.Controls.Control.Template%2A>. L'esempio seguente crea una finestra di messaggio che indica il valore di larghezza effettiva del <xref:System.Windows.Controls.Grid> all'interno del modello di controllo:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: trovare elementi generati da un oggetto DataTemplate](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Ambiti dei nomi XAML WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [Strutture ad albero in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
