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
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004109"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="6a606-102">Procedura: Enumerare i tipi di carattere installati</span><span class="sxs-lookup"><span data-stu-id="6a606-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="6a606-103">Il <xref:System.Drawing.Text.InstalledFontCollection> classe eredita dal <xref:System.Drawing.Text.FontCollection> classe base astratta.</span><span class="sxs-lookup"><span data-stu-id="6a606-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="6a606-104">È possibile usare un <xref:System.Drawing.Text.InstalledFontCollection> oggetto da enumerare i tipi di carattere installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6a606-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="6a606-105">Il <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà di un <xref:System.Drawing.Text.InstalledFontCollection> oggetto è una matrice di <xref:System.Drawing.FontFamily> oggetti.</span><span class="sxs-lookup"><span data-stu-id="6a606-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a606-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a606-106">Example</span></span>  
 <span data-ttu-id="6a606-107">Nell'esempio seguente elenca i nomi di tutte le famiglie di caratteri installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="6a606-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="6a606-108">Il codice recupera le <xref:System.Drawing.FontFamily.Name%2A> proprietà della ognuno <xref:System.Drawing.FontFamily> oggetto nella matrice restituita dal <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="6a606-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="6a606-109">Come vengono recuperati i nomi di famiglia, questi vengono concatenati di elenco in formato delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="6a606-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="6a606-110">Il <xref:System.Drawing.Graphics.DrawString%2A> metodo di <xref:System.Drawing.Graphics> classe consente di disegnare l'elenco delimitato da virgole in un rettangolo.</span><span class="sxs-lookup"><span data-stu-id="6a606-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="6a606-111">Se si esegue il codice di esempio, l'output sarà simile a quello illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="6a606-111">If you run the example code, the output will be similar to that shown in the following illustration:</span></span>  
  
 ![Screenshot che mostra le famiglie di tipi di carattere installati.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a606-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6a606-113">Compiling the Code</span></span>  
 <span data-ttu-id="6a606-114">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="6a606-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="6a606-115">Inoltre, è necessario importare il <xref:System.Drawing.Text> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6a606-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a606-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a606-116">See also</span></span>

- [<span data-ttu-id="6a606-117">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="6a606-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
