---
title: 'Procedura: Specificare la direzione del binding'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 023cd42ad5fb321e7ffa65f08673cb4145f49af4
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817905"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Procedura: Specificare la direzione dell'associazione

Questo esempio spiega come specificare se il binding aggiorna solo la proprietà della destinazione del binding (destinazione), dell'origine del binding (origine) o entrambe.  
  
## <a name="example"></a>Esempio  
 Utilizzare la <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> proprietà per specificare la direzione del binding. Di seguito sono riportate le opzioni disponibili per gli aggiornamenti di binding:  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>Aggiorna la proprietà di destinazione o la proprietà ogni volta che la proprietà di destinazione o la proprietà di origine viene modificata.  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType>Aggiorna la proprietà di destinazione solo quando la proprietà di origine viene modificata.  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType>Aggiorna la proprietà di destinazione solo quando l'applicazione viene avviata <xref:System.Windows.FrameworkElement.DataContext%2A> o quando subisce una modifica.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType>Aggiorna la proprietà di origine quando viene modificata la proprietà di destinazione.  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType>determina l'utilizzo <xref:System.Windows.Data.Binding.Mode%2A> del valore predefinito della proprietà target.  
  
 Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Data.BindingMode>.  
  
 Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Per rilevare le modifiche apportate <xref:System.Windows.Data.BindingMode.OneWay> all' <xref:System.Windows.Data.BindingMode.TwoWay> origine (applicabili alle associazioni e), l'origine deve implementare un meccanismo appropriato di <xref:System.ComponentModel.INotifyPropertyChanged>notifica delle modifiche alle proprietà, ad esempio. Per un esempio di implementazione di <xref:System.ComponentModel.INotifyPropertyChanged>, vedere [implementare una notifica di modifica delle proprietà](how-to-implement-property-change-notification.md).  
  
 Per <xref:System.Windows.Data.BindingMode.TwoWay> le <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni o, è possibile controllare l'intervallo degli aggiornamenti di origine impostando la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà. Per altre informazioni, vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
