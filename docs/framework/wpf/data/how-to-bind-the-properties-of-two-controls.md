---
title: "Procedura: Eseguire l'associazione delle proprietà di due controlli"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: f3355969d0f12f0f3ed9b49bdb7efa6913c5e4c4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372100"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="658ce-102">Procedura: Eseguire l'associazione delle proprietà di due controlli</span><span class="sxs-lookup"><span data-stu-id="658ce-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="658ce-103">Questo esempio viene illustrato come associare la proprietà di un controllo di un'istanza a quella di un altro usando il <xref:System.Windows.Data.Binding.ElementName%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="658ce-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="658ce-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="658ce-104">Example</span></span>  
 <span data-ttu-id="658ce-105">Nell'esempio seguente viene illustrato come associare le <xref:System.Windows.Controls.Panel.Background%2A> proprietà di un <xref:System.Windows.Controls.Canvas> per il <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="658ce-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="658ce-106">proprietà di un <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="658ce-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="658ce-107">Dopo il rendering questo esempio avrà l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="658ce-107">When this example is rendered it looks like the following:</span></span>  
  
 <span data-ttu-id="658ce-108">![Un canvas con uno sfondo verde](./media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span><span class="sxs-lookup"><span data-stu-id="658ce-108">![A canvas with a green background](./media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span></span>  
  
 <span data-ttu-id="658ce-109">**Nota** le proprietà di destinazione del binding (in questo esempio, il <xref:System.Windows.Controls.Panel.Background%2A> proprietà) deve essere una proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="658ce-109">**Note** The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="658ce-110">Per altre informazioni, vedere la [panoramica del data binding](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="658ce-110">For more information, see [Data Binding Overview](data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658ce-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="658ce-111">See also</span></span>
- [<span data-ttu-id="658ce-112">Specificare l'origine di associazione</span><span class="sxs-lookup"><span data-stu-id="658ce-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="658ce-113">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="658ce-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
