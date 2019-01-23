---
title: "Procedura: Eseguire l'associazione delle proprietà di due controlli"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 63584872c027ed3a80698304a7221c161c8d928a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570252"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Procedura: Eseguire l'associazione delle proprietà di due controlli
Questo esempio viene illustrato come associare la proprietà di un controllo di un'istanza a quella di un altro usando il <xref:System.Windows.Data.Binding.ElementName%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare le <xref:System.Windows.Controls.Panel.Background%2A> proprietà di un <xref:System.Windows.Controls.Canvas> per il <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Dopo il rendering questo esempio avrà l'aspetto seguente:  
  
 ![Un canvas con uno sfondo verde](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")  
  
 **Nota** le proprietà di destinazione del binding (in questo esempio, il <xref:System.Windows.Controls.Panel.Background%2A> proprietà) deve essere una proprietà di dipendenza. Per altre informazioni, vedere la [panoramica del data binding](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>Vedere anche
- [Specificare l'origine di associazione](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
