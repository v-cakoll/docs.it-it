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
ms.openlocfilehash: b71783f2d061c9139de4449d8e0106eb00345894
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740171"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Procedura: eseguire un hit test utilizzando un contenitore di host Win32
È possibile creare oggetti visivi in una finestra Win32 fornendo un contenitore della finestra host per gli oggetti visivi. Per fornire la gestione degli eventi per gli oggetti visivi contenuti, elaborare i messaggi passati al ciclo del filtro messaggi del contenitore della finestra host. Per altre informazioni su come ospitare oggetti visivi in una finestra Win32, vedere [esercitazione: hosting di oggetti visivi in un'applicazione Win32](tutorial-hosting-visual-objects-in-a-win32-application.md) .  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene illustrato come configurare i gestori di eventi del mouse per una finestra Win32 utilizzata come contenitore host per gli oggetti visivi.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 Nell'esempio seguente viene illustrato come impostare un hit test in risposta a intercettare eventi del mouse specifici.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 L'oggetto <xref:System.Windows.Interop.HwndSource> presenta [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenuto all'interno di una finestra Win32. Il valore della proprietà <xref:System.Windows.Interop.HwndSource.RootVisual%2A> dell'oggetto <xref:System.Windows.Interop.HwndSource> rappresenta il nodo di primo livello nella gerarchia della struttura ad albero visuale.  
  
 Per l'esempio completo sugli oggetti hit testing con un contenitore host Win32, vedere [esempio di hit test con interoperatività Win32](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndSource>
- [Hit testing a livello visivo](hit-testing-in-the-visual-layer.md)
- [Esercitazione: hosting di oggetti visivi in un'applicazione Win32](tutorial-hosting-visual-objects-in-a-win32-application.md)
