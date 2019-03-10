---
title: 'Procedura: Enumerare i tipi di carattere installati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 34234ee0400e1d2ca36f2f559b63d282f590ca0d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709883"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="57565-102">Procedura: Enumerare i tipi di carattere installati</span><span class="sxs-lookup"><span data-stu-id="57565-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="57565-103">Il <xref:System.Drawing.Text.InstalledFontCollection> classe eredita dal <xref:System.Drawing.Text.FontCollection> classe base astratta.</span><span class="sxs-lookup"><span data-stu-id="57565-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="57565-104">È possibile usare un <xref:System.Drawing.Text.InstalledFontCollection> oggetto da enumerare i tipi di carattere installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="57565-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="57565-105">Il <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà di un <xref:System.Drawing.Text.InstalledFontCollection> oggetto è una matrice di <xref:System.Drawing.FontFamily> oggetti.</span><span class="sxs-lookup"><span data-stu-id="57565-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57565-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="57565-106">Example</span></span>  
 <span data-ttu-id="57565-107">Nell'esempio seguente elenca i nomi di tutte le famiglie di caratteri installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="57565-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="57565-108">Il codice recupera le <xref:System.Drawing.FontFamily.Name%2A> proprietà della ognuno <xref:System.Drawing.FontFamily> oggetto nella matrice restituita dal <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="57565-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="57565-109">Come vengono recuperati i nomi di famiglia, questi vengono concatenati di elenco in formato delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="57565-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="57565-110">Il <xref:System.Drawing.Graphics.DrawString%2A> metodo di <xref:System.Drawing.Graphics> classe consente di disegnare l'elenco delimitato da virgole in un rettangolo.</span><span class="sxs-lookup"><span data-stu-id="57565-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="57565-111">Se si esegue il codice di esempio, l'output sarà simile a quello illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="57565-111">If you run the example code, the output will be similar to that shown in the following illustration.</span></span>  
  
 <span data-ttu-id="57565-112">![I tipi di carattere installati](./media/csfontstext6.png "csfontstext6")</span><span class="sxs-lookup"><span data-stu-id="57565-112">![Installed Fonts](./media/csfontstext6.png "csfontstext6")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57565-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="57565-113">Compiling the Code</span></span>  
 <span data-ttu-id="57565-114">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="57565-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="57565-115">Inoltre, è necessario importare il <xref:System.Drawing.Text> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="57565-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57565-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57565-116">See also</span></span>
- [<span data-ttu-id="57565-117">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="57565-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
