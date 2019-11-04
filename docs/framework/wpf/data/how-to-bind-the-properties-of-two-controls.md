---
title: "Procedura: eseguire l'associazione delle proprietà di due controlli"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459174"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="5e150-102">Procedura: eseguire l'associazione delle proprietà di due controlli</span><span class="sxs-lookup"><span data-stu-id="5e150-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="5e150-103">Questo esempio illustra come associare la proprietà di un controllo di cui è stata creata un'istanza a quella di un altro usando la proprietà <xref:System.Windows.Data.Binding.ElementName%2A>.</span><span class="sxs-lookup"><span data-stu-id="5e150-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e150-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e150-104">Example</span></span>  
 <span data-ttu-id="5e150-105">Nell'esempio seguente viene illustrato come associare la proprietà <xref:System.Windows.Controls.Panel.Background%2A> di un <xref:System.Windows.Controls.Canvas> al <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="5e150-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="5e150-106">Proprietà di un <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="5e150-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="5e150-107">Dopo il rendering questo esempio avrà l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="5e150-107">When this example is rendered it looks like the following:</span></span>  
  
![Screenshot che mostra una casella combinata con il valore verde selezionato e un quadrato verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="5e150-109">La proprietà di destinazione del binding (in questo esempio, la proprietà <xref:System.Windows.Controls.Panel.Background%2A>) deve essere una proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="5e150-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="5e150-110">Per altre informazioni, vedere la [panoramica del data binding](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5e150-110">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e150-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e150-111">See also</span></span>

- [<span data-ttu-id="5e150-112">Specificare l'origine di associazione</span><span class="sxs-lookup"><span data-stu-id="5e150-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="5e150-113">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="5e150-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
