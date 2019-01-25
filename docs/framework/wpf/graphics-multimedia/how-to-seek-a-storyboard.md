---
title: 'Procedura: Cercare uno storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: 440b2dd157b56a1616f7137b1e311cb981b33861
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604457"
---
# <a name="how-to-seek-a-storyboard"></a>Procedura: Cercare uno storyboard
Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> metodo di un <xref:System.Windows.Media.Animation.Storyboard> per passare a una posizione qualsiasi nell'animazione di uno storyboard.  
  
## <a name="example"></a>Esempio  
 Di seguito è indicato il markup XAML per l'esempio.  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Di seguito è indicato il codice usato con il codice XAML riportato sopra.  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- [Cercare uno storyboard in modo sincrono](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md)
