---
title: 'Procedura: Modificare la proprietà TextWrapping a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
ms.openlocfilehash: 70dc73fe16ebb98e466c4363e5ac26562329dcd4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362266"
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a><span data-ttu-id="8886f-102">Procedura: Modificare la proprietà TextWrapping a livello di codice</span><span class="sxs-lookup"><span data-stu-id="8886f-102">How to: Change the TextWrapping Property Programmatically</span></span>
## <a name="example"></a><span data-ttu-id="8886f-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="8886f-103">Example</span></span>  
 <span data-ttu-id="8886f-104">Esempio di codice seguente viene illustrato come modificare il valore della <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> proprietà a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="8886f-104">The following code example shows how to change the value of the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> property programmatically.</span></span>  
  
 <span data-ttu-id="8886f-105">Tre <xref:System.Windows.Controls.Button> elementi vengono posizionati all'interno di un <xref:System.Windows.Controls.StackPanel> elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8886f-105">Three <xref:System.Windows.Controls.Button> elements are placed within a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="8886f-106">Ciascuna <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento per un <xref:System.Windows.Controls.Button> corrisponde a un gestore eventi nel codice.</span><span class="sxs-lookup"><span data-stu-id="8886f-106">Each <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for a <xref:System.Windows.Controls.Button> corresponds with an event handler in the code.</span></span> <span data-ttu-id="8886f-107">I gestori eventi usano lo stesso nome di <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> valore verranno applicate a `txt2` quando fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="8886f-107">The event handlers use the same name as the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> value they will apply to `txt2` when the button is clicked.</span></span> <span data-ttu-id="8886f-108">Inoltre, il testo nel `txt1` (una <xref:System.Windows.Controls.TextBlock> non visualizzati nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) viene aggiornato per riflettere la modifica della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8886f-108">Also, the text in `txt1` (a <xref:System.Windows.Controls.TextBlock> not shown in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) is updated to reflect the change in the property.</span></span>  
  
 [!code-xaml[TextWrapProperty#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="8886f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8886f-109">See also</span></span>
- <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>
- <xref:System.Windows.TextWrapping>
