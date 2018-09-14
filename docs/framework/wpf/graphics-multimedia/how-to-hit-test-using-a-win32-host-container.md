---
title: 'Procedura: eseguire un hit test utilizzando un contenitore di host Win32'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: bb175e0f8aeb126b7f7fa85d5af1c4afcf5bea61
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45590635"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Procedura: eseguire un hit test utilizzando un contenitore di host Win32
È possibile creare oggetti visivi all'interno di un [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] finestra fornendo un finestra contenitore host per gli oggetti visivi. Per fornire la gestione degli eventi per gli oggetti visivi contenuti, elaborare i messaggi passati al ciclo del filtro messaggi del contenitore della finestra host. Fare riferimento a [esercitazione: Hosting di oggetti visivi in un'applicazione Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) per altre informazioni su come ospitare oggetti visivi in un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato come configurare gestori di eventi del mouse per una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra che viene usato come un contenitore host per gli oggetti visivi.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 Nell'esempio seguente viene illustrato come impostare un hit test in risposta all'intercettazione di specifici eventi del mouse.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Il <xref:System.Windows.Interop.HwndSource> oggetto presenta [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenuto all'interno di un [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] finestra. Il valore della <xref:System.Windows.Interop.HwndSource.RootVisual%2A> proprietà del <xref:System.Windows.Interop.HwndSource> oggetto rappresenta il nodo superiore nella gerarchia di struttura ad albero visuale.  
  
 Per l'esempio completo sull'hit testing di oggetti usando un contenitore host Win32, vedere [Hit Test with Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.HwndSource>  
 [Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Esercitazione: hosting di oggetti visivi in un'applicazione Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
