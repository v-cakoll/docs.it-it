---
title: "Procedura: eseguire l'associazione delle proprietà di due controlli"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: d38c473b8c4d3f71f1e3decd4f66be248665c57b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974809"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="7f76a-102">Procedura: eseguire l'associazione delle proprietà di due controlli</span><span class="sxs-lookup"><span data-stu-id="7f76a-102">How to: Bind the Properties of Two Controls</span></span>

<span data-ttu-id="7f76a-103">Questo esempio illustra come associare la proprietà di un controllo di cui è stata creata un'istanza a quella di un altro usando la proprietà <xref:System.Windows.Data.Binding.ElementName%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f76a-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="7f76a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f76a-104">Example</span></span>

<span data-ttu-id="7f76a-105">Nell'esempio seguente viene illustrato come associare la proprietà <xref:System.Windows.Controls.Panel.Background%2A> di un <xref:System.Windows.Controls.Canvas> alla proprietà [SelectedItem. Content](xref:System.Windows.Controls.ContentControl.Content%2A) di un <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="7f76a-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the [SelectedItem.Content](xref:System.Windows.Controls.ContentControl.Content%2A) property of a <xref:System.Windows.Controls.ComboBox>:</span></span>

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

<span data-ttu-id="7f76a-106">Dopo il rendering questo esempio avrà l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="7f76a-106">When this example is rendered it looks like the following:</span></span>

![Screenshot che mostra una casella combinata con il valore verde selezionato e un quadrato verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="7f76a-108">La proprietà di destinazione del binding (in questo esempio, la proprietà <xref:System.Windows.Controls.Panel.Background%2A>) deve essere una proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="7f76a-108">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="7f76a-109">Per altre informazioni, vedere la [panoramica del data binding](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7f76a-109">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7f76a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f76a-110">See also</span></span>

- [<span data-ttu-id="7f76a-111">Specificare l'origine di associazione</span><span class="sxs-lookup"><span data-stu-id="7f76a-111">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="7f76a-112">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="7f76a-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
