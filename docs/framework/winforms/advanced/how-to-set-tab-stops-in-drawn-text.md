---
title: 'Procedura: Impostare tabulazioni nel testo disegnato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 68dbebfc4fab773fe749f9443d0c61883099d2ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197490"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="0c7ce-102">Procedura: Impostare tabulazioni nel testo disegnato</span><span class="sxs-lookup"><span data-stu-id="0c7ce-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="0c7ce-103">È possibile impostare punti di tabulazione per il testo chiamando il <xref:System.Drawing.StringFormat.SetTabStops%2A> metodo di un <xref:System.Drawing.StringFormat> oggetto e quindi passandolo <xref:System.Drawing.StringFormat> dell'oggetto per il <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="0c7ce-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c7ce-104">Il <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> fa uso non supporta l'aggiunta di tabulazione al testo disegnato, anche se è possibile espandere la scheda esistente viene interrotto il <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span><span class="sxs-lookup"><span data-stu-id="0c7ce-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c7ce-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c7ce-105">Example</span></span>  
 <span data-ttu-id="0c7ce-106">Nell'esempio seguente imposta punti di tabulazione in corrispondenza di 150, 250 e 350.</span><span class="sxs-lookup"><span data-stu-id="0c7ce-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="0c7ce-107">Quindi, il codice visualizza un elenco dei nomi e i punteggi di test.</span><span class="sxs-lookup"><span data-stu-id="0c7ce-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="0c7ce-108">La figura seguente mostra il testo a schede:</span><span class="sxs-lookup"><span data-stu-id="0c7ce-108">The following illustration shows the tabbed text:</span></span>  
  
 ![Screenshot che mostra un elenco dei nomi e i punteggi.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="0c7ce-110">Il codice seguente passa due argomenti per il <xref:System.Drawing.StringFormat.SetTabStops%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="0c7ce-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="0c7ce-111">Il secondo argomento è una matrice che contiene gli offset di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="0c7ce-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="0c7ce-112">Il primo argomento passato a <xref:System.Drawing.StringFormat.SetTabStops%2A> è 0, che indica che il primo offset nella matrice vengono misurate da posizione 0, il bordo sinistro del rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="0c7ce-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0c7ce-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0c7ce-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="0c7ce-114">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="0c7ce-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7ce-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c7ce-115">See also</span></span>

- [<span data-ttu-id="0c7ce-116">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="0c7ce-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="0c7ce-117">Procedura: Disegnare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="0c7ce-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
