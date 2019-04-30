---
title: 'Procedura: Creare e usare un oggetto GridLengthConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 498d2b9c531f391f4cbeb1478469a99d381deec7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050987"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a><span data-ttu-id="e1ada-102">Procedura: Creare e usare un oggetto GridLengthConverter</span><span class="sxs-lookup"><span data-stu-id="e1ada-102">How to: Create and Use a GridLengthConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="e1ada-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1ada-103">Example</span></span>  
 <span data-ttu-id="e1ada-104">Nell'esempio seguente viene illustrato come creare e usare un'istanza di <xref:System.Windows.GridLengthConverter>.</span><span class="sxs-lookup"><span data-stu-id="e1ada-104">The following example shows how to create and use an instance of <xref:System.Windows.GridLengthConverter>.</span></span> <span data-ttu-id="e1ada-105">L'esempio definisce un metodo personalizzato denominato `changeCol`, che passa il <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.GridLengthConverter> che converte il <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Windows.GridLength>.</span><span class="sxs-lookup"><span data-stu-id="e1ada-105">The example defines a custom method called `changeCol`, which passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.GridLengthConverter> that converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.GridLength>.</span></span> <span data-ttu-id="e1ada-106">Il valore convertito viene quindi passato nuovamente come valore dei <xref:System.Windows.Controls.ColumnDefinition.Width%2A> proprietà del <xref:System.Windows.Controls.ColumnDefinition> elemento.</span><span class="sxs-lookup"><span data-stu-id="e1ada-106">The converted value is then passed back as the value of the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> property of the <xref:System.Windows.Controls.ColumnDefinition> element.</span></span>  
  
 <span data-ttu-id="e1ada-107">L'esempio definisce anche un secondo metodo personalizzato, denominato `changeColVal`.</span><span class="sxs-lookup"><span data-stu-id="e1ada-107">The example also defines a second custom method, called `changeColVal`.</span></span> <span data-ttu-id="e1ada-108">Converte questo metodo personalizzato le <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> di un <xref:System.Windows.Controls.Slider> a un <xref:System.String> e quindi passa tale valore al <xref:System.Windows.Controls.ColumnDefinition> come il <xref:System.Windows.Controls.ColumnDefinition.Width%2A> dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e1ada-108">This custom method converts the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> of a <xref:System.Windows.Controls.Slider> to a <xref:System.String> and then passes that value back to the <xref:System.Windows.Controls.ColumnDefinition> as the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the element.</span></span>  
  
 <span data-ttu-id="e1ada-109">Si noti che un oggetto separato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file definisce il contenuto di un <xref:System.Windows.Controls.ListBoxItem>.</span><span class="sxs-lookup"><span data-stu-id="e1ada-109">Note that a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file defines the contents of a <xref:System.Windows.Controls.ListBoxItem>.</span></span>  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e1ada-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1ada-110">See also</span></span>

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
