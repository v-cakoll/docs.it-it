---
title: 'Procedura: Associare uno strumento decorativo a un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: e8c7eb929042bfe1455bfc9bf459fc466de5c397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923501"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>Procedura: Associare uno strumento decorativo a un elemento
Questo esempio illustra come associare uno strumento decorativo a livello di codice a <xref:System.Windows.UIElement>un oggetto specificato.  
  
## <a name="example"></a>Esempio  
 Per associare uno strumento decorativo a un <xref:System.Windows.UIElement>particolare, attenersi alla seguente procedura:  
  
1. Chiamare il `static` metodo <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per ottenere un <xref:System.Windows.Documents.AdornerLayer> oggetto per l' <xref:System.Windows.UIElement> oggetto da decorare. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>esamina la struttura ad albero visuale, iniziando dall' **oggetto UIElement**specificato e restituisce il primo livello dello strumento decorativo rilevato. (se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).  
  
2. Chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare lo strumento decorativo visuale all' **oggetto UIElement**di destinazione.  
  
 Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) a <xref:System.Windows.Controls.TextBox> un *oggetto denominato TextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sugli strumenti decorativi](adorners-overview.md)
