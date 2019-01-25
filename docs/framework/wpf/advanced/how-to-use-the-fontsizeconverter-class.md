---
title: 'Procedura: Utilizzare la classe FontSizeConverter'
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: 7cb76ad4ffe4b4574a48212240b852e1f2253088
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741899"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="6be83-102">Procedura: Utilizzare la classe FontSizeConverter</span><span class="sxs-lookup"><span data-stu-id="6be83-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="6be83-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="6be83-103">Example</span></span>  
 <span data-ttu-id="6be83-104">In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.FontSizeConverter> e usarlo per modificare una dimensione del carattere.</span><span class="sxs-lookup"><span data-stu-id="6be83-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="6be83-105">L'esempio definisce un metodo personalizzato denominato `changeSize` che converte il contenuto di un <xref:System.Windows.Controls.ListBoxItem>, come definito in un oggetto separato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, a un'istanza di <xref:System.Double>e successivamente in un <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6be83-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="6be83-106">Questo metodo passa il <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.FontSizeConverter> oggetto, che converte le <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="6be83-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="6be83-107">Questo valore viene quindi passato nuovamente come valore dei <xref:System.Windows.Controls.TextBlock.FontSize%2A> proprietà del <xref:System.Windows.Controls.TextBlock> elemento.</span><span class="sxs-lookup"><span data-stu-id="6be83-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="6be83-108">In questo esempio definisce anche un secondo metodo personalizzato che viene chiamato `changeFamily`.</span><span class="sxs-lookup"><span data-stu-id="6be83-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="6be83-109">Questo metodo converte il <xref:System.Windows.Controls.ContentControl.Content%2A> del <xref:System.Windows.Controls.ListBoxItem> per un <xref:System.String>e quindi passa tale valore per il <xref:System.Windows.Controls.TextBlock.FontFamily%2A> proprietà del <xref:System.Windows.Controls.TextBlock> elemento.</span><span class="sxs-lookup"><span data-stu-id="6be83-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="6be83-110">Questo esempio non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="6be83-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6be83-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6be83-111">See also</span></span>
- <xref:System.Windows.FontSizeConverter>
