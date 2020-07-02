---
title: "Procedura: specificare l'origine del binding"
description: Informazioni su come specificare l'origine del binding tramite questo esempio nell'Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 55d47757-2648-4a52-987f-b767953f168c
ms.openlocfilehash: 02f27da007ebe8c5985f91b83adfba7d3d00219a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621665"
---
# <a name="how-to-specify-the-binding-source"></a>Procedura: specificare l'origine del binding
Nel data binding l'oggetto origine di binding fa riferimento all'oggetto da cui si ottengono i dati. Questo argomento descrive i vari modi per specificare l'origine del binding.  
  
## <a name="example"></a>Esempio  
 Se si associano più proprietà a un'origine comune, è consigliabile usare la proprietà `DataContext`, che offre un modo pratico per definire un ambito in cui tutte le proprietà associate ai dati ereditano un'origine comune.  
  
 Nell'esempio seguente il contesto dei dati viene stabilito nell'elemento radice dell'applicazione. In questo modo tutti gli elementi figlio ereditano il contesto dei dati. I dati per il binding derivano da una classe di dati personalizzata, `NetIncome`, a cui viene direttamente fatto riferimento tramite un mapping e assegnata la chiave di risorsa di `incomeDataSource`.  
  
 [!code-xaml[DirectionalBinding#DataContext1](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext1)]  
[!code-xaml[DirectionalBinding#DataContext2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext2)]  
  
 L'esempio seguente illustra la definizione della classe `NetIncome`.  
  
 [!code-csharp[DirectionalBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/billsdata.cs#dataobject)]
 [!code-vb[DirectionalBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DirectionalBinding/VisualBasic/NetIncome.vb#dataobject)]  
  
> [!NOTE]
> L'esempio precedente crea un'istanza dell'oggetto nel markup e la usa come risorsa. Per eseguire il binding a un oggetto di cui è già stata creata un'istanza nel codice, è necessario impostare la proprietà `DataContext` a livello di codice. Per un esempio, vedere [Rendere i dati disponibili per l'associazione in XAML](how-to-make-data-available-for-binding-in-xaml.md).  
  
 In alternativa, se si desidera specificare l'origine nei singoli binding in modo esplicito, sono disponibili le opzioni seguenti. Queste hanno precedenza sul contesto dei dati ereditato.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Data.Binding.Source%2A>|Usare questa proprietà per impostare l'origine su un'istanza di un oggetto. Se non è necessaria la funzionalità di definizione di un ambito in cui diverse proprietà ereditano lo stesso contesto dati, è possibile utilizzare la <xref:System.Windows.Data.Binding.Source%2A> proprietà anziché la `DataContext` Proprietà. Per altre informazioni, vedere <xref:System.Windows.Data.Binding.Source%2A>.|  
|<xref:System.Windows.Data.Binding.RelativeSource%2A>|Risulta utile se si desidera specificare l'origine rispetto alla posizione in cui si trova la destinazione del binding. Alcuni scenari comuni in cui è possibile usare questa proprietà: se si desidera associare una proprietà dell'elemento a un'altra proprietà dello stesso elemento oppure se si definisce un binding in uno stile o un modello. Per altre informazioni, vedere <xref:System.Windows.Data.Binding.RelativeSource%2A>.|  
|<xref:System.Windows.Data.Binding.ElementName%2A>|Specificare una stringa che rappresenta l'elemento a cui si desidera eseguire il binding. Risulta utile se si desidera eseguire il binding alla proprietà di un altro elemento dell'applicazione, Ad esempio, se si vuole usare un oggetto <xref:System.Windows.Controls.Slider> per controllare l'altezza di un altro controllo nell'applicazione o se si vuole associare l'oggetto <xref:System.Windows.Controls.ContentControl.Content%2A> del controllo alla <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> proprietà del <xref:System.Windows.Controls.ListBox> controllo. Per altre informazioni, vedere <xref:System.Windows.Data.Binding.ElementName%2A>.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.DataContext%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.DataContext%2A?displayProperty=nameWithType>
- [Ereditarietà del valore della proprietà](../advanced/property-value-inheritance.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Cenni preliminari sulle dichiarazioni di associazione](binding-declarations-overview.md)
- [Procedure](data-binding-how-to-topics.md)
