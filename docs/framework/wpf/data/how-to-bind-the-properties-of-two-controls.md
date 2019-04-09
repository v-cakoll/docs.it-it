---
title: 'Procedura: Eseguire il binding delle proprietà di due controlli'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 0dd7b817b632758cfca8b5c45d88e333510485f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222065"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="c16f0-102">Procedura: Eseguire il binding delle proprietà di due controlli</span><span class="sxs-lookup"><span data-stu-id="c16f0-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="c16f0-103">Questo esempio viene illustrato come associare la proprietà di un controllo di un'istanza a quella di un altro usando il <xref:System.Windows.Data.Binding.ElementName%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c16f0-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c16f0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c16f0-104">Example</span></span>  
 <span data-ttu-id="c16f0-105">Nell'esempio seguente viene illustrato come associare le <xref:System.Windows.Controls.Panel.Background%2A> proprietà di un <xref:System.Windows.Controls.Canvas> per il <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="c16f0-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.</span></span><xref:System.Windows.Controls.ContentControl.Content%2A> <span data-ttu-id="c16f0-106">proprietà di un <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="c16f0-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="c16f0-107">Dopo il rendering questo esempio avrà l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="c16f0-107">When this example is rendered it looks like the following:</span></span>  
  
 <span data-ttu-id="c16f0-108">![Un canvas con uno sfondo verde](./media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span><span class="sxs-lookup"><span data-stu-id="c16f0-108">![A canvas with a green background](./media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span></span>  
  
 <span data-ttu-id="c16f0-109">**Nota** le proprietà di destinazione del binding (in questo esempio, il <xref:System.Windows.Controls.Panel.Background%2A> proprietà) deve essere una proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="c16f0-109">**Note** The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="c16f0-110">Per altre informazioni, vedere la [panoramica del data binding](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c16f0-110">For more information, see [Data Binding Overview](data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c16f0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c16f0-111">See also</span></span>

- [<span data-ttu-id="c16f0-112">Specificare l'origine di binding</span><span class="sxs-lookup"><span data-stu-id="c16f0-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="c16f0-113">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="c16f0-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
