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
ms.openlocfilehash: 526305f32280fb75e95538b9014c34c11ed8bffa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556640"
---
# <a name="how-to-convert-bound-data"></a>Procedura: convertire i dati associati
In questo esempio viene illustrato come applicare la conversione in dati utilizzati nelle associazioni.  
  
 Per convertire i dati durante l'associazione, è necessario creare una classe che implementa il <xref:System.Windows.Data.IValueConverter> interfaccia, che include il <xref:System.Windows.Data.IValueConverter.Convert%2A> e <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> metodi.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l'implementazione di un convertitore di tipi di data che converte il valore di data passato in modo che visualizza solo l'anno, mese e giorno. Quando si implementa il <xref:System.Windows.Data.IValueConverter> interfaccia, è buona norma decorare l'implementazione con un <xref:System.Windows.Data.ValueConversionAttribute> attributo per indicare allo sviluppo di strumenti di tipi di dati coinvolti nella conversione, come nell'esempio seguente:  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Dopo aver creato un convertitore, è possibile aggiungere come risorsa nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file. Nell'esempio seguente, *src* esegue il mapping allo spazio dei nomi in cui *DateConverter* è definito.  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Infine, è possibile utilizzare il convertitore nell'associazione utilizzando la sintassi seguente. Nell'esempio seguente, il contenuto di testo di <xref:System.Windows.Controls.TextBlock> è associato a *StartDate*, che è una proprietà di un'origine dati esterna.  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Le risorse di stile a cui fa riferimento nell'esempio precedente sono definite in una sezione di risorsa non è stata illustrata in questo argomento.  
  
## <a name="see-also"></a>Vedere anche  
 [Implementare la convalida dell'associazione](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
