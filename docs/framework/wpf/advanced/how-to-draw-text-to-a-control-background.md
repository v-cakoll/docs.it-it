---
title: 'Procedura: creare testo sullo sfondo di un controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424378"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="12eed-102">Procedura: creare testo sullo sfondo di un controllo</span><span class="sxs-lookup"><span data-stu-id="12eed-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="12eed-103">È possibile disegnare il testo direttamente sullo sfondo di un controllo convertendo una stringa di testo in un oggetto <xref:System.Windows.Media.FormattedText>, quindi disegnando l'oggetto nella <xref:System.Windows.Media.DrawingContext>del controllo.</span><span class="sxs-lookup"><span data-stu-id="12eed-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="12eed-104">È anche possibile usare questa tecnica per disegnare sullo sfondo di oggetti derivati da <xref:System.Windows.Controls.Panel>, ad esempio <xref:System.Windows.Controls.Canvas> e <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="12eed-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="12eed-105">![Screenshot dei controlli che visualizzano testo come sfondo.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="12eed-105">![Screenshot of controls displaying text as background.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span></span>  
<span data-ttu-id="12eed-106">Esempio di controlli con sfondi di testo personalizzati</span><span class="sxs-lookup"><span data-stu-id="12eed-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="12eed-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="12eed-107">Example</span></span>  
 <span data-ttu-id="12eed-108">Per creare uno sfondo di un controllo, creare un nuovo oggetto <xref:System.Windows.Media.DrawingBrush> e creare il testo convertito nel <xref:System.Windows.Media.DrawingContext>dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="12eed-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="12eed-109">Assegnare quindi la nuova <xref:System.Windows.Media.DrawingBrush> alla proprietà background del controllo.</span><span class="sxs-lookup"><span data-stu-id="12eed-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="12eed-110">Nell'esempio di codice seguente viene illustrato come creare un oggetto <xref:System.Windows.Media.FormattedText> e come eseguire il progetto sullo sfondo di un oggetto <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="12eed-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="12eed-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12eed-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="12eed-112">Disegno di testo formattato</span><span class="sxs-lookup"><span data-stu-id="12eed-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
