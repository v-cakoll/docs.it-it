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
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="cc632-102">Procedura: Migliorare le prestazioni di scorrimento di un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="cc632-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="cc632-103">Se un <xref:System.Windows.Controls.ListBox> contiene molti elementi, la risposta dell'interfaccia utente può essere lenta se un utente scorre il <xref:System.Windows.Controls.ListBox> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="cc632-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="cc632-104">È possibile migliorare le prestazioni dei <xref:System.Windows.Controls.ListBox> quando l'utente scorre, impostare il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cc632-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc632-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc632-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="cc632-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc632-106">Description</span></span>  
<span data-ttu-id="cc632-107">L'esempio seguente crea una <xref:System.Windows.Controls.ListBox> e imposta la `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per migliorare le prestazioni durante lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="cc632-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="cc632-108">Codice</span><span class="sxs-lookup"><span data-stu-id="cc632-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="cc632-109">Nell'esempio seguente mostra i dati che usa l'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="cc632-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
