---
title: 'Procedura: Enumerare il contenuto del disegno di un oggetto visivo'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 4f0afc1075fe66c7f154fcef3cd883709db55316
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108004"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>Procedura: Enumerare il contenuto del disegno di un oggetto visivo
Il <xref:System.Windows.Media.Drawing> oggetto forniscono un modello a oggetti per l'enumerazione del contenuto di un <xref:System.Windows.Media.Visual>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> metodo per recuperare il <xref:System.Windows.Media.DrawingGroup> pari a un <xref:System.Windows.Media.Visual> ed enumerarlo.  
  
> [!NOTE]
>  Quando si enumerano il contenuto dell'oggetto visivo, si recuperano <xref:System.Windows.Media.Drawing> oggetti e non la rappresentazione sottostante dei dati di rendering come un elenco di istruzioni di grafica vettoriale. Per altre informazioni, vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
