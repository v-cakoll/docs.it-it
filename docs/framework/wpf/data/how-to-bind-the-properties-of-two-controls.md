---
title: 'Procedura: Eseguire il binding delle proprietà di due controlli'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 332e8e0dfa30ff7aff27c95652f07446baf6511a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754043"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Procedura: Eseguire il binding delle proprietà di due controlli
Questo esempio viene illustrato come associare la proprietà di un controllo di un'istanza a quella di un altro usando il <xref:System.Windows.Data.Binding.ElementName%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare le <xref:System.Windows.Controls.Panel.Background%2A> proprietà di un <xref:System.Windows.Controls.Canvas> per il <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Dopo il rendering questo esempio avrà l'aspetto seguente:  
  
![Screenshot che mostra una casella combinata finestra con il valore di colore verde selezionato e un quadrato verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> La proprietà di destinazione del binding (in questo esempio, il <xref:System.Windows.Controls.Panel.Background%2A> proprietà) deve essere una proprietà di dipendenza. Per altre informazioni, vedere la [panoramica del data binding](data-binding-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Specificare l'origine di associazione](how-to-specify-the-binding-source.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
