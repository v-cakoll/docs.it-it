---
title: 'Procedura: convertire i dati associati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458861"
---
# <a name="how-to-convert-bound-data"></a>Procedura: convertire i dati associati
In questo esempio viene illustrato come applicare la conversione ai dati utilizzati nelle associazioni.  
  
 Per convertire i dati durante l'associazione, è necessario creare una classe che implementi l'interfaccia <xref:System.Windows.Data.IValueConverter>, che include i metodi <xref:System.Windows.Data.IValueConverter.Convert%2A> e <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l'implementazione di un convertitore di data che converte il valore di data passato in modo da visualizzare solo l'anno, il mese e il giorno. Quando si implementa l'interfaccia <xref:System.Windows.Data.IValueConverter>, è consigliabile decorare l'implementazione con un attributo <xref:System.Windows.Data.ValueConversionAttribute> per indicare agli strumenti di sviluppo i tipi di dati necessari per la conversione, come nell'esempio seguente:  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Una volta creato un convertitore, è possibile aggiungerlo come risorsa nel file di [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Nell'esempio seguente *src* esegue il mapping allo spazio dei nomi in cui è definito *DateConverter* .  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Infine, è possibile usare il convertitore nell'associazione usando la sintassi seguente. Nell'esempio seguente il contenuto di testo del <xref:System.Windows.Controls.TextBlock> viene associato a *StartDate*, che è una proprietà di un'origine dati esterna.  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Le risorse di stile a cui viene fatto riferimento nell'esempio precedente sono definite in una sezione delle risorse non illustrata in questo argomento.  
  
## <a name="see-also"></a>Vedere anche

- [Implementare la convalida dell'associazione](how-to-implement-binding-validation.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
