---
title: 'Procedura: Adornare gli elementi figlio di un oggetto Panel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: ae039243ded93eb2bc7f85f9f07fad1dbe0eac2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544978"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Procedura: Adornare gli elementi figlio di un oggetto Panel
Questo esempio illustra come associare programmaticamente uno strumento decorativo agli elementi figlio di un elemento specificato <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Esempio  
 Per associare uno strumento decorativo agli elementi figlio di un <xref:System.Windows.Controls.Panel>, seguire questa procedura:  
  
1.  Dichiarare una nuova <xref:System.Windows.Documents.AdornerLayer> oggetto e chiamare il `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> metodo per trovare un livello dello strumento decorativo per l'elemento cui figli rappresentino da decorare.  
  
2.  Enumerare gli elementi figlio dell'elemento padre e chiamata di <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare uno strumento decorativo a ogni elemento figlio.  
  
 Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) per gli elementi figlio di un <xref:System.Windows.Controls.StackPanel> denominate *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica sugli strumenti decorativi](../../../../docs/framework/wpf/controls/adorners-overview.md)
