---
title: 'Procedura: migliorare le prestazioni di scorrimento di un controllo ListBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: 224b996ad97d9a71ce43023143b68c2ab5b8467b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a>Procedura: migliorare le prestazioni di scorrimento di un controllo ListBox
Se un <xref:System.Windows.Controls.ListBox> contiene molti elementi, la risposta dell'interfaccia utente può essere lenta quando un utente scorre il <xref:System.Windows.Controls.ListBox> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento. È possibile migliorare le prestazioni del <xref:System.Windows.Controls.ListBox> quando l'utente scorre impostando il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ListBox> e imposta il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per migliorare le prestazioni durante lo scorrimento.  
  
## <a name="code"></a>Codice  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 Nell'esempio seguente mostra i dati che utilizza l'esempio precedente.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
