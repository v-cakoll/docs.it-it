---
title: 'Procedura: Specificare la direzione del binding'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 4334ed178e7f2ed90928db6b434eb8c9fee77bf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931481"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Procedura: Specificare la direzione del binding
Questo esempio spiega come specificare se il binding aggiorna solo la proprietà della destinazione del binding (destinazione), dell'origine del binding (origine) o entrambe.  
  
## <a name="example"></a>Esempio  
 Si utilizza il <xref:System.Windows.Data.Binding.Mode%2A> proprietà per specificare la direzione dell'associazione. L'elenco di enumerazione seguente mostra le opzioni disponibili per gli aggiornamenti di binding:  
  
- <xref:System.Windows.Data.BindingMode.TwoWay> Aggiorna la proprietà di destinazione o la proprietà ogni volta che cambia la proprietà di destinazione o la proprietà di origine.  
  
- <xref:System.Windows.Data.BindingMode.OneWay> Aggiorna la proprietà di destinazione solo quando la proprietà di origine viene modificata.  
  
- <xref:System.Windows.Data.BindingMode.OneTime> Aggiorna la proprietà di destinazione solo all'avvio dell'applicazione o quando il <xref:System.Windows.FrameworkElement.DataContext%2A> subisce una modifica.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource> Aggiorna la proprietà di origine quando cambia la proprietà di destinazione.  
  
- <xref:System.Windows.Data.BindingMode.Default> fa sì che il valore predefinito <xref:System.Windows.Data.Binding.Mode%2A> valore della proprietà di destinazione da usare.  
  
 Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Data.BindingMode>.  
  
 Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Per rilevare le modifiche di origine (applicabile per <xref:System.Windows.Data.BindingMode.OneWay> e <xref:System.Windows.Data.BindingMode.TwoWay> associazioni), l'origine deve implementare un meccanismo di notifica di modifica proprietà appropriato, ad esempio <xref:System.ComponentModel.INotifyPropertyChanged>. Visualizzare [implementare la notifica di modifica proprietà](how-to-implement-property-change-notification.md) per un esempio di un <xref:System.ComponentModel.INotifyPropertyChanged> implementazione.  
  
 Per la <xref:System.Windows.Data.BindingMode.TwoWay> oppure <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni, è possibile controllare la tempistica degli aggiornamenti di origine, impostando il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà. Per altre informazioni, vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
