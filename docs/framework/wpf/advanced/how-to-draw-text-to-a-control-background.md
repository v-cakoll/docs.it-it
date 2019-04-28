---
title: 'Procedura: Disegnare testo sullo sfondo di un controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 76449c88f9a720741c8ed61255e04a40e6a8613f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776206"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="5cbdc-102">Procedura: Disegnare testo sullo sfondo di un controllo</span><span class="sxs-lookup"><span data-stu-id="5cbdc-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="5cbdc-103">È possibile disegnare testo direttamente sullo sfondo di un controllo convertendo una stringa di testo a un <xref:System.Windows.Media.FormattedText> dell'oggetto e quindi disegnare l'oggetto per il controllo <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="5cbdc-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="5cbdc-104">È anche possibile usare questa tecnica per disegnare sullo sfondo di oggetti derivati da <xref:System.Windows.Controls.Panel>, ad esempio <xref:System.Windows.Controls.Canvas> e <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="5cbdc-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="5cbdc-105">![Controlli che visualizzano testo come sfondo](./media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="5cbdc-105">![Controls displaying text as background](./media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="5cbdc-106">Esempio di controlli con sfondi di testo personalizzati</span><span class="sxs-lookup"><span data-stu-id="5cbdc-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cbdc-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5cbdc-107">Example</span></span>  
 <span data-ttu-id="5cbdc-108">Per disegnare sullo sfondo di un controllo, creare una nuova <xref:System.Windows.Media.DrawingBrush> dell'oggetto e disegnare il testo convertito dell'oggetto <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="5cbdc-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="5cbdc-109">Quindi, assegnare al nuovo <xref:System.Windows.Media.DrawingBrush> alla proprietà dello sfondo del controllo.</span><span class="sxs-lookup"><span data-stu-id="5cbdc-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="5cbdc-110">Esempio di codice seguente viene illustrato come creare un <xref:System.Windows.Media.FormattedText> dell'oggetto e disegnare lo sfondo di un <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Button> oggetto.</span><span class="sxs-lookup"><span data-stu-id="5cbdc-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="5cbdc-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cbdc-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="5cbdc-112">Disegno di testo formattato</span><span class="sxs-lookup"><span data-stu-id="5cbdc-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
