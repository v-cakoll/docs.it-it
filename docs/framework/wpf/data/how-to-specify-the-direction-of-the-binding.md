---
title: 'Procedura: specificare la direzione di associazione'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 8f7d843382ee3409047d7cf9549267d582883984
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459101"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Procedura: specificare la direzione dell'associazione

Questo esempio spiega come specificare se il binding aggiorna solo la proprietà della destinazione del binding (destinazione), dell'origine del binding (origine) o entrambe.  
  
## <a name="example"></a>Esempio  
 Utilizzare la proprietà <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> per specificare la direzione del binding. Di seguito sono riportate le opzioni disponibili per gli aggiornamenti di binding:  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> aggiorna la proprietà di destinazione o la proprietà ogni volta che la proprietà di destinazione o la proprietà di origine viene modificata.  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> aggiorna la proprietà di destinazione solo quando la proprietà di origine viene modificata.  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> aggiorna la proprietà di destinazione solo quando l'applicazione viene avviata o quando il <xref:System.Windows.FrameworkElement.DataContext%2A> subisce una modifica.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> aggiorna la proprietà di origine quando viene modificata la proprietà di destinazione.  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causa l'utilizzo del valore predefinito <xref:System.Windows.Data.Binding.Mode%2A> della proprietà target.  
  
 Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Data.BindingMode>.  
  
 Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Per rilevare le modifiche dell'origine (applicabili alle associazioni <xref:System.Windows.Data.BindingMode.OneWay> e <xref:System.Windows.Data.BindingMode.TwoWay>), è necessario che l'origine implementi un meccanismo di notifica delle modifiche di proprietà appropriato, ad esempio <xref:System.ComponentModel.INotifyPropertyChanged>. Per un esempio di implementazione di <xref:System.ComponentModel.INotifyPropertyChanged>, vedere [implementare una notifica di modifica delle proprietà](how-to-implement-property-change-notification.md) .  
  
 Per i binding <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource>, è possibile controllare l'intervallo degli aggiornamenti di origine impostando la proprietà <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>. Per altre informazioni, vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
