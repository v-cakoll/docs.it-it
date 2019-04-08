---
title: 'Procedura: Usare un oggetto ThicknessConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: ebfb8642a01f6d602f4e5ffa58fde6a8ee0b4e1f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075951"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="9abec-102">Procedura: Usare un oggetto ThicknessConverter</span><span class="sxs-lookup"><span data-stu-id="9abec-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="9abec-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="9abec-103">Example</span></span>  
 <span data-ttu-id="9abec-104">In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.ThicknessConverter> e usarlo per modificare lo spessore di un bordo.</span><span class="sxs-lookup"><span data-stu-id="9abec-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="9abec-105">L'esempio definisce un metodo personalizzato denominato `changeThickness`; questo metodo converte prima di tutto il contenuto di un <xref:System.Windows.Controls.ListBoxItem>, come definito in un oggetto separato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, a un'istanza di <xref:System.Windows.Thickness>e lo converte in un secondo momento il contenuto in un <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="9abec-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="9abec-106">Questo metodo passa il <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.ThicknessConverter> oggetto, che converte le <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Windows.Thickness>.</span><span class="sxs-lookup"><span data-stu-id="9abec-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="9abec-107">Questo valore viene quindi passato nuovamente come valore dei <xref:System.Windows.Controls.Border.BorderThickness%2A> proprietà del <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="9abec-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="9abec-108">Questo esempio non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="9abec-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9abec-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9abec-109">See also</span></span>

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="9abec-110">Procedura: Modificare la proprietà Margin</span><span class="sxs-lookup"><span data-stu-id="9abec-110">How to: Change the Margin Property</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))
- [<span data-ttu-id="9abec-111">Procedura: Convertire un oggetto ListBoxItem in un nuovo tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9abec-111">How to: Convert a ListBoxItem to a new Data Type</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))
- [<span data-ttu-id="9abec-112">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="9abec-112">Panels Overview</span></span>](../controls/panels-overview.md)
