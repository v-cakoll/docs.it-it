---
title: 'Procedura: Eseguire il binding delle proprietà di due controlli'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 0dd7b817b632758cfca8b5c45d88e333510485f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222065"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Procedura: Eseguire il binding delle proprietà di due controlli
Questo esempio viene illustrato come associare la proprietà di un controllo di un'istanza a quella di un altro usando il <xref:System.Windows.Data.Binding.ElementName%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare le <xref:System.Windows.Controls.Panel.Background%2A> proprietà di un <xref:System.Windows.Controls.Canvas> per il <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Dopo il rendering questo esempio avrà l'aspetto seguente:  
  
 ![Un canvas con uno sfondo verde](./media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")  
  
 **Nota** le proprietà di destinazione del binding (in questo esempio, il <xref:System.Windows.Controls.Panel.Background%2A> proprietà) deve essere una proprietà di dipendenza. Per altre informazioni, vedere la [panoramica del data binding](data-binding-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Specificare l'origine di associazione](how-to-specify-the-binding-source.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
