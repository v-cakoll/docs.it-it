---
title: "Procedura: eseguire l'associazione a un'enumerazione"
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454447"
---
# <a name="how-to-bind-to-an-enumeration"></a>Procedura: eseguire l'associazione a un'enumerazione
In questo esempio viene illustrato come eseguire l'associazione a un'enumerazione mediante l'associazione al metodo GetValues dell'enumerazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il <xref:System.Windows.Controls.ListBox> Visualizza l'elenco dei valori di enumerazione <xref:System.Windows.HorizontalAlignment> tramite data binding. Il <xref:System.Windows.Controls.ListBox> e il <xref:System.Windows.Controls.Button> sono associati in modo che sia possibile modificare il valore della proprietà <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> della <xref:System.Windows.Controls.Button> selezionando un valore nella <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Vedere anche

- [Eseguire l'associazione a un metodo](how-to-bind-to-a-method.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
