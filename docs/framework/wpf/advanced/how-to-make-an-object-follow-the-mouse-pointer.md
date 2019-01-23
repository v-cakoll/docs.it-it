---
title: 'Procedura: Fare in modo che un oggetto segua il puntatore del mouse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 3e39b9459fbc94c9b7684ffd7c597363e46ad717
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541820"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Procedura: Fare in modo che un oggetto segua il puntatore del mouse
In questo esempio viene illustrato come modificare le dimensioni di un oggetto quando il puntatore del mouse viene spostato sullo schermo.  
  
 L'esempio include un' [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file che crea il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] e un file code-behind che crea il gestore dell'evento.  
  
## <a name="example"></a>Esempio  
 Quanto segue [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], che è costituito un <xref:System.Windows.Shapes.Ellipse> all'interno di una <xref:System.Windows.Controls.StackPanel>e associa il gestore eventi per il <xref:System.Windows.UIElement.MouseMove> evento.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Crea il codice seguente sotto il <xref:System.Windows.UIElement.MouseMove> gestore dell'evento.  Quando si sposta il puntatore del mouse, l'altezza e la larghezza del <xref:System.Windows.Shapes.Ellipse> vengono aumentate e ridotte.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sull'input](../../../../docs/framework/wpf/advanced/input-overview.md)
