---
title: 'Procedura: Convertire dati associati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: 40699bec1c6cd775f7f8495b7a49eda15fb2ed83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093800"
---
# <a name="how-to-convert-bound-data"></a>Procedura: Convertire dati associati
In questo esempio viene illustrato come applicare la conversione in dati utilizzati nelle associazioni.  
  
 Per convertire i dati durante l'associazione, è necessario creare una classe che implementa il <xref:System.Windows.Data.IValueConverter> interfaccia, che include le <xref:System.Windows.Data.IValueConverter.Convert%2A> e <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> metodi.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l'implementazione di un convertitore di data che converte il valore di data passato in modo che venga visualizzato solo l'anno, mese e giorno. Quando si implementa il <xref:System.Windows.Data.IValueConverter> interfaccia, è buona norma per decorare l'implementazione con una <xref:System.Windows.Data.ValueConversionAttribute> attributo per indicare allo sviluppo di strumenti i tipi di dati coinvolti nella conversione, come nell'esempio seguente:  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Dopo aver creato un convertitore di tipi, è possibile aggiungerlo come una risorsa nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file. Nell'esempio riportato di seguito *src* esegue il mapping allo spazio dei nomi in cui *DateConverter* è definito.  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Infine, è possibile usare il convertitore dell'associazione utilizzando la sintassi seguente. Nell'esempio seguente, il contenuto di testo il <xref:System.Windows.Controls.TextBlock> è associato a *StartDate*, che è una proprietà di un'origine dati esterna.  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Le risorse di stile a cui fa riferimento l'esempio precedente sono definite in una sezione di risorse non illustrata in questo argomento.  
  
## <a name="see-also"></a>Vedere anche

- [Implementare la convalida dell'associazione](how-to-implement-binding-validation.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
