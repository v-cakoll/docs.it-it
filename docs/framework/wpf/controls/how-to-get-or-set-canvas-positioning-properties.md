---
title: 'Procedura: Ottenere o impostare le proprietà di posizionamento delle aree di disegno'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194409"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="76cae-102">Procedura: Ottenere o impostare le proprietà di posizionamento delle aree di disegno</span><span class="sxs-lookup"><span data-stu-id="76cae-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="76cae-103">In questo esempio viene illustrato come utilizzare i metodi di posizionamento del <xref:System.Windows.Controls.Canvas> elemento per posizionare il contenuto figlio.</span><span class="sxs-lookup"><span data-stu-id="76cae-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="76cae-104">Questo esempio viene usato il contenuto in un <xref:System.Windows.Controls.ListBoxItem> per rappresentare valori di posizionamento e converte i valori in istanze di <xref:System.Double>, che è un argomento obbligatorio per il posizionamento.</span><span class="sxs-lookup"><span data-stu-id="76cae-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="76cae-105">I valori vengono quindi convertiti in stringhe e visualizzati come testo in un <xref:System.Windows.Controls.TextBlock> elemento usando la <xref:System.Windows.Controls.Canvas.GetLeft%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="76cae-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76cae-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="76cae-106">Example</span></span>  
 <span data-ttu-id="76cae-107">L'esempio seguente crea una <xref:System.Windows.Controls.ListBox> elemento che dispone di undici selezionabile <xref:System.Windows.Controls.ListBoxItem> elementi.</span><span class="sxs-lookup"><span data-stu-id="76cae-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="76cae-108">Il <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> trigger di evento di `ChangeLeft` metodo personalizzato che definisce il blocco di codice successivo.</span><span class="sxs-lookup"><span data-stu-id="76cae-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="76cae-109">Ogni <xref:System.Windows.Controls.ListBoxItem> rappresenta un <xref:System.Double> valore, ovvero uno degli argomenti che le <xref:System.Windows.Controls.Canvas.SetLeft%2A> metodo <xref:System.Windows.Controls.Canvas> accetta.</span><span class="sxs-lookup"><span data-stu-id="76cae-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="76cae-110">Per usare un <xref:System.Windows.Controls.ListBoxItem> per rappresentare un'istanza di <xref:System.Double>, è prima necessario convertire il <xref:System.Windows.Controls.ListBoxItem> al tipo di dati corretto.</span><span class="sxs-lookup"><span data-stu-id="76cae-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="76cae-111">Quando un utente modifica il <xref:System.Windows.Controls.ListBox> selezione, viene richiamato il `ChangeLeft` metodo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="76cae-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="76cae-112">Questo metodo passa il <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.LengthConverter> oggetto, che converte il <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Double> (si noti che questo valore è già stato convertito in un <xref:System.String> utilizzando il <xref:System.Windows.Controls.Control.ToString%2A> metodo).</span><span class="sxs-lookup"><span data-stu-id="76cae-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="76cae-113">Questo valore viene quindi passato al <xref:System.Windows.Controls.Canvas.SetLeft%2A> e <xref:System.Windows.Controls.Canvas.GetLeft%2A> metodi del <xref:System.Windows.Controls.Canvas> per modificare la posizione del `text1` oggetto.</span><span class="sxs-lookup"><span data-stu-id="76cae-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="76cae-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76cae-114">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [<span data-ttu-id="76cae-115">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="76cae-115">Panels Overview</span></span>](panels-overview.md)
