---
title: 'Procedura: produrre un valore in base a un elenco di elementi associati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: da183a34eb85de54b1e3f54f8d14c09e25640165
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459688"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Procedura: produrre un valore in base a un elenco di elementi associati
<xref:System.Windows.Data.MultiBinding> consente di associare una proprietà di destinazione del binding a un elenco di proprietà di origine, quindi applicare la logica per produrre un valore con gli input specificati. Questo esempio illustra come usare <xref:System.Windows.Data.MultiBinding>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, `NameListData` fa riferimento a una raccolta di oggetti `PersonName`, che contengono due proprietà: `firstName` e `lastName`. Nell'esempio seguente viene generato un <xref:System.Windows.Controls.TextBlock> che mostra il nome e il cognome di una persona con il cognome per primo.  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Per comprendere come viene generato il formato con il cognome prima del nome, osservare l'implementazione di `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 L'oggetto `NameConverter` implementa l'interfaccia <xref:System.Windows.Data.IMultiValueConverter>. `NameConverter` accetta i valori dei singoli binding e li archivia nella matrice di oggetti valore. L'ordine in cui vengono visualizzati gli elementi <xref:System.Windows.Data.Binding> sotto l'elemento <xref:System.Windows.Data.MultiBinding> è l'ordine in cui tali valori vengono archiviati nella matrice. Al valore dell'attributo <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> viene fatto riferimento dall'argomento Parameter del metodo <xref:System.Windows.Data.MultiBinding.Converter%2A>, che esegue un'opzione sul parametro per determinare come formattare il nome.  
  
## <a name="see-also"></a>Vedere anche

- [Convertire i dati associati](how-to-convert-bound-data.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
