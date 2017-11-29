---
title: 'Procedura: specificare la direzione di associazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdcda02a61f0114bfbbe5d5c411cb397cddcf683
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Procedura: specificare la direzione di associazione
Questo esempio spiega come specificare se il binding aggiorna solo la proprietà della destinazione del binding (destinazione), dell'origine del binding (origine) o entrambe.  
  
## <a name="example"></a>Esempio  
 Utilizzare il <xref:System.Windows.Data.Binding.Mode%2A> proprietà per specificare la direzione dell'associazione. L'elenco di enumerazione seguente mostra le opzioni disponibili per gli aggiornamenti di binding:  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay>Aggiorna la proprietà di destinazione o la proprietà ogni volta che cambia la proprietà di destinazione o la proprietà di origine.  
  
-   <xref:System.Windows.Data.BindingMode.OneWay>Aggiorna la proprietà di destinazione solo quando la proprietà di origine viene modificata.  
  
-   <xref:System.Windows.Data.BindingMode.OneTime>Aggiorna la proprietà di destinazione solo all'avvio dell'applicazione o quando il <xref:System.Windows.FrameworkElement.DataContext%2A> subisce una modifica.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource>Aggiorna la proprietà di origine quando viene modificata la proprietà di destinazione.  
  
-   <xref:System.Windows.Data.BindingMode.Default>fa sì che il valore predefinito <xref:System.Windows.Data.Binding.Mode%2A> valore della proprietà di destinazione da utilizzare.  
  
 Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Data.BindingMode>.  
  
 Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Per rilevare le modifiche di origine (applicabile a <xref:System.Windows.Data.BindingMode.OneWay> e <xref:System.Windows.Data.BindingMode.TwoWay> associazioni), l'origine deve implementare un meccanismo di notifica di modifica proprietà appropriato, ad esempio <xref:System.ComponentModel.INotifyPropertyChanged>. Vedere [implementano la notifica di modifiche](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) per un esempio di un <xref:System.ComponentModel.INotifyPropertyChanged> implementazione.  
  
 Per <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni, è possibile controllare la tempistica degli aggiornamenti di origine mediante l'impostazione di <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà. Per altre informazioni, vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.Binding>  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
