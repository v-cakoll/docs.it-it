---
title: "Procedura: eseguire l'associazione delle proprietà di due controlli"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459174"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Procedura: eseguire l'associazione delle proprietà di due controlli
Questo esempio illustra come associare la proprietà di un controllo di cui è stata creata un'istanza a quella di un altro usando la proprietà <xref:System.Windows.Data.Binding.ElementName%2A>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare la proprietà <xref:System.Windows.Controls.Panel.Background%2A> di un <xref:System.Windows.Controls.Canvas> al <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> Proprietà di un <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Dopo il rendering questo esempio avrà l'aspetto seguente:  
  
![Screenshot che mostra una casella combinata con il valore verde selezionato e un quadrato verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> La proprietà di destinazione del binding (in questo esempio, la proprietà <xref:System.Windows.Controls.Panel.Background%2A>) deve essere una proprietà di dipendenza. Per altre informazioni, vedere la [panoramica del data binding](../../../desktop-wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Specificare l'origine di associazione](how-to-specify-the-binding-source.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
