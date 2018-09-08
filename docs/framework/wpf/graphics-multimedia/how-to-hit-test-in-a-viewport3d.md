---
title: 'Procedura: eseguire un hit test in un oggetto Viewport3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 297fe17b8844f7542255afcfe442fbf9b7a0d59d
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44140658"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>Procedura: eseguire un hit test in un oggetto Viewport3D
Questo esempio illustra come eseguire un hit test per gli oggetti visivi 3D in un <xref:System.Windows.Controls.Viewport3D>.  
  
 Poiché <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> restituisce informazioni 2D e 3D, è possibile scorrere i risultati del test per leggere i risultati solo 3D.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 Il <xref:System.Windows.Media.HitTestResultBehavior> nel codice seguente determina come vengono elaborati i risultati dell'hit test.  `UpdateResultInfo` e `UpdateMaterial` sono metodi definiti in locale.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a>Vedere anche  
 [3D esempio di Hit Testing](https://go.microsoft.com/fwlink/?LinkID=159959)
