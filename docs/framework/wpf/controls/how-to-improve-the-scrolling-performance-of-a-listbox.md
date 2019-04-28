---
title: 'Procedura: Migliorare le prestazioni di scorrimento di un controllo ListBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: a9d1ca1d8ac2ef830984408f3052eb0ed0987c5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770864"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a>Procedura: Migliorare le prestazioni di scorrimento di un controllo ListBox
Se un <xref:System.Windows.Controls.ListBox> contiene molti elementi, la risposta dell'interfaccia utente può essere lenta se un utente scorre il <xref:System.Windows.Controls.ListBox> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento. È possibile migliorare le prestazioni dei <xref:System.Windows.Controls.ListBox> quando l'utente scorre, impostare il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
L'esempio seguente crea una <xref:System.Windows.Controls.ListBox> e imposta la `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per migliorare le prestazioni durante lo scorrimento.  
  
## <a name="code"></a>Codice  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 Nell'esempio seguente mostra i dati che usa l'esempio precedente.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
