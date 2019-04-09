---
title: "Procedura: Eseguire il binding a un'enumerazione"
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 5026261366d6abde82790f05780d8ba2c29c4a49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210022"
---
# <a name="how-to-bind-to-an-enumeration"></a>Procedura: Eseguire il binding a un'enumerazione
In questo esempio viene illustrato come eseguire l'associazione a un'enumerazione tramite l'associazione al metodo GetValues dell'enumerazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il <xref:System.Windows.Controls.ListBox> Visualizza l'elenco di <xref:System.Windows.HorizontalAlignment> valori di enumerazione tramite associazione dati. Il <xref:System.Windows.Controls.ListBox> e il <xref:System.Windows.Controls.Button> sono associati in modo che sia possibile modificare le <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore della proprietà il <xref:System.Windows.Controls.Button> selezionando un valore nel <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Vedere anche

- [Eseguire il binding a un metodo](how-to-bind-to-a-method.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative](data-binding-how-to-topics.md)
