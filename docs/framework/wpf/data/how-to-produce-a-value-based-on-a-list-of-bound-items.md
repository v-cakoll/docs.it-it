---
title: 'Procedura: produrre un valore in base a un elenco di elementi associati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d16a198ed78c1ffd9dcaad595e9cc9be3cb2de0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Procedura: produrre un valore in base a un elenco di elementi associati
<xref:System.Windows.Data.MultiBinding>Consente di associare una proprietà di destinazione dell'associazione a un elenco di proprietà dell'origine e quindi applicare la logica per produrre un valore con gli input specificati. In questo esempio viene illustrato come utilizzare <xref:System.Windows.Data.MultiBinding>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, `NameListData` fa riferimento a una raccolta di oggetti `PersonName`, che contengono due proprietà: `firstName` e `lastName`. L'esempio seguente produce un <xref:System.Windows.Controls.TextBlock> che mostra i nomi e il cognome di una persona con il nome dell'ultimo prima.  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Per comprendere come viene generato il formato con il cognome prima del nome, osservare l'implementazione di `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 L'oggetto `NameConverter` implementa l'interfaccia <xref:System.Windows.Data.IMultiValueConverter>. `NameConverter` accetta i valori dei singoli binding e li archivia nella matrice di oggetti valore. L'ordine in cui il <xref:System.Windows.Data.Binding> gli elementi vengono visualizzati sotto il <xref:System.Windows.Data.MultiBinding> elemento è l'ordine in cui sono archiviati tali valori nella matrice. Il valore della <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> fa riferimento l'argomento di parametro dell'attributo di <xref:System.Windows.Data.MultiBinding.Converter%2A> (metodo), che esegue una modifica del parametro per determinare la modalità di formattazione del nome.  
  
## <a name="see-also"></a>Vedere anche  
 [Convertire i dati associati](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
