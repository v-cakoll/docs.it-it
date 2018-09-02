---
title: 'Procedura: utilizzare un oggetto ThicknessConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 6c8f9e83468a7b189b96efca2e175c0f3fe0dfff
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399353"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="c43fa-102">Procedura: utilizzare un oggetto ThicknessConverter</span><span class="sxs-lookup"><span data-stu-id="c43fa-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="c43fa-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="c43fa-103">Example</span></span>  
 <span data-ttu-id="c43fa-104">In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.ThicknessConverter> e usarlo per modificare lo spessore di un bordo.</span><span class="sxs-lookup"><span data-stu-id="c43fa-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="c43fa-105">L'esempio definisce un metodo personalizzato denominato `changeThickness`; questo metodo converte prima di tutto il contenuto di un <xref:System.Windows.Controls.ListBoxItem>, come definito in un oggetto separato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, a un'istanza di <xref:System.Windows.Thickness>e lo converte in un secondo momento il contenuto in un <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="c43fa-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="c43fa-106">Questo metodo passa il <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.ThicknessConverter> oggetto, che converte le <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Windows.Thickness>.</span><span class="sxs-lookup"><span data-stu-id="c43fa-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="c43fa-107">Questo valore viene quindi passato nuovamente come valore dei <xref:System.Windows.Controls.Border.BorderThickness%2A> proprietà del <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="c43fa-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="c43fa-108">Questo esempio non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="c43fa-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c43fa-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c43fa-109">See Also</span></span>  
 <xref:System.Windows.Thickness>  
 <xref:System.Windows.ThicknessConverter>  
 <xref:System.Windows.Controls.Border>  
 [<span data-ttu-id="c43fa-110">Procedura: modificare la proprietà Margin</span><span class="sxs-lookup"><span data-stu-id="c43fa-110">How to: Change the Margin Property</span></span>](https://msdn.microsoft.com/library/8a313efd-5f99-4097-b4c1-8fa49d8379a2)  
 [<span data-ttu-id="c43fa-111">Procedura: convertire un oggetto ListBoxItem in un nuovo tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c43fa-111">How to: Convert a ListBoxItem to a new Data Type</span></span>](https://msdn.microsoft.com/library/7a080b88-184e-4b27-bb61-d42bafba9727)  
 [<span data-ttu-id="c43fa-112">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="c43fa-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
