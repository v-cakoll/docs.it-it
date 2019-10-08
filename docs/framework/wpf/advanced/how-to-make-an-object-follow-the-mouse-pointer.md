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
ms.openlocfilehash: 4ef3028b6c71b94a593d168ad6570c4aec12b86b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005071"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Procedura: Fare in modo che un oggetto segua il puntatore del mouse
Questo esempio Mostra come modificare le dimensioni di un oggetto quando il puntatore del mouse viene spostato sullo schermo.  
  
 Nell'esempio è incluso un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che crea il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] e un file code-behind che crea il gestore eventi.  
  
## <a name="example"></a>Esempio  
 Il codice XAML seguente crea il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], che è costituito da un <xref:System.Windows.Shapes.Ellipse> all'interno di un <xref:System.Windows.Controls.StackPanel> e connette il gestore eventi per l'evento <xref:System.Windows.UIElement.MouseMove>.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Il codice sottostante seguente crea il gestore dell'evento <xref:System.Windows.UIElement.MouseMove>.  Quando il puntatore del mouse viene spostato, l'altezza e la larghezza del <xref:System.Windows.Shapes.Ellipse> vengono aumentate e diminuite.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)
