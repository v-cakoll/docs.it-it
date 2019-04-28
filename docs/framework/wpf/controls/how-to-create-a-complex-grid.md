---
title: Come creare una griglia complessa
description: Un esempio su come usare un controllo griglia per creare un layout simile a un calendario mensile.
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: dd17dfeea85e2b404f7a284f93faceec63145b1f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910995"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="b7245-103">Come creare una griglia complessa</span><span class="sxs-lookup"><span data-stu-id="b7245-103">How to create a complex Grid</span></span>

<span data-ttu-id="b7245-104">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Controls.Grid> controllo per creare un layout simile a un calendario mensile.</span><span class="sxs-lookup"><span data-stu-id="b7245-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="b7245-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7245-105">Example</span></span>

<span data-ttu-id="b7245-106">L'esempio seguente definisce le otto righe e otto colonne usando il <xref:System.Windows.Controls.RowDefinition> e <xref:System.Windows.Controls.ColumnDefinition> classi.</span><span class="sxs-lookup"><span data-stu-id="b7245-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="b7245-107">Usa il <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> associate, insieme a <xref:System.Windows.Shapes.Rectangle> elementi, che è riempiono gli sfondi delle varie colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="b7245-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="b7245-108">Questa progettazione è possibile perché può esistere più di un elemento in ogni cella in una <xref:System.Windows.Controls.Grid>, una differenza essenziale tra <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Documents.Table>.</span><span class="sxs-lookup"><span data-stu-id="b7245-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="b7245-109">L'esempio Usa le sfumature verticale a <xref:System.Windows.Shapes.Shape.Fill%2A> le colonne e righe per migliorare la presentazione visiva e migliorare la leggibilità del calendario.</span><span class="sxs-lookup"><span data-stu-id="b7245-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="b7245-110">Nello stile <xref:System.Windows.Controls.TextBlock> elementi rappresentano le date e giorni della settimana.</span><span class="sxs-lookup"><span data-stu-id="b7245-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="b7245-111"><xref:System.Windows.Controls.TextBlock> gli elementi vengono posizionati all'interno delle celle mediante i <xref:System.Windows.FrameworkElement.Margin%2A> proprietà e le proprietà di allineamento definiti al suo interno lo stile per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7245-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="b7245-112">L'immagine seguente mostra il controllo risultante, un calendario personalizzabile:</span><span class="sxs-lookup"><span data-stu-id="b7245-112">The following image shows the resulting control, a customizable calendar:</span></span>

![Screenshot del controllo risulta](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="b7245-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7245-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="b7245-115">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="b7245-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="b7245-116">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="b7245-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="b7245-117">Cenni preliminari sull'elemento Table</span><span class="sxs-lookup"><span data-stu-id="b7245-117">Table Overview</span></span>](../advanced/table-overview.md)