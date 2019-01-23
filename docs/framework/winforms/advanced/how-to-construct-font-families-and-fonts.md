---
title: 'Procedura: Costruire i tipi di carattere e famiglie di caratteri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 6f939ab90252697d09d594e4d9300ec101c8f2e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540676"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="a2591-102">Procedura: Costruire i tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="a2591-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="a2591-103">Raggruppa i tipi di carattere con lo stesso carattere tipografico, ma diversi stili in famiglie di caratteri.</span><span class="sxs-lookup"><span data-stu-id="a2591-103">groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="a2591-104">Ad esempio, il tipo di carattere Arial contiene i tipi di carattere seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2591-104">For example, the Arial font family contains the following fonts:</span></span>  
  
-   <span data-ttu-id="a2591-105">Arial normale</span><span class="sxs-lookup"><span data-stu-id="a2591-105">Arial Regular</span></span>  
  
-   <span data-ttu-id="a2591-106">Arial in grassetto</span><span class="sxs-lookup"><span data-stu-id="a2591-106">Arial Bold</span></span>  
  
-   <span data-ttu-id="a2591-107">Arial corsivo</span><span class="sxs-lookup"><span data-stu-id="a2591-107">Arial Italic</span></span>  
  
-   <span data-ttu-id="a2591-108">Arial grassetto corsivo</span><span class="sxs-lookup"><span data-stu-id="a2591-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="a2591-109">vengono utilizzati quattro stili per creare i gruppi: normale, grassetto, corsivo e grassetto corsivo.</span><span class="sxs-lookup"><span data-stu-id="a2591-109">uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="a2591-110">Aggettivi, ad esempio *restringere* e *arrotondato* non vengono considerati gli stili, piuttosto fanno parte del nome della famiglia.</span><span class="sxs-lookup"><span data-stu-id="a2591-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="a2591-111">Ad esempio, Arial ristretto è una famiglia di caratteri con i membri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2591-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
-   <span data-ttu-id="a2591-112">Arial normale ridotta</span><span class="sxs-lookup"><span data-stu-id="a2591-112">Arial Narrow Regular</span></span>  
  
-   <span data-ttu-id="a2591-113">Arial "narrow" grassetto</span><span class="sxs-lookup"><span data-stu-id="a2591-113">Arial Narrow Bold</span></span>  
  
-   <span data-ttu-id="a2591-114">Corsivo Narrow Arial</span><span class="sxs-lookup"><span data-stu-id="a2591-114">Arial Narrow Italic</span></span>  
  
-   <span data-ttu-id="a2591-115">Arial Narrow grassetto corsivo</span><span class="sxs-lookup"><span data-stu-id="a2591-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="a2591-116">Prima di poter creare testo con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è necessario costruire una <xref:System.Drawing.FontFamily> oggetto e un <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="a2591-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="a2591-117">Il <xref:System.Drawing.FontFamily> oggetto specifica il carattere tipografico (ad esempio, Arial) e il <xref:System.Drawing.Font> oggetto specifica le dimensioni, stile e unità.</span><span class="sxs-lookup"><span data-stu-id="a2591-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2591-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2591-118">Example</span></span>  
 <span data-ttu-id="a2591-119">Nell'esempio seguente crea uno stile regolare del tipo di carattere Arial con dimensioni pari a 16 pixel.</span><span class="sxs-lookup"><span data-stu-id="a2591-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="a2591-120">Nel codice seguente, il primo argomento passato per il <xref:System.Drawing.Font.%23ctor%2A> costruttore è la <xref:System.Drawing.FontFamily> oggetto.</span><span class="sxs-lookup"><span data-stu-id="a2591-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="a2591-121">Il secondo argomento specifica le dimensioni del font misurata nelle unità specificate dal quarto argomento.</span><span class="sxs-lookup"><span data-stu-id="a2591-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="a2591-122">Il terzo argomento identificato lo stile.</span><span class="sxs-lookup"><span data-stu-id="a2591-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="a2591-123"><xref:System.Drawing.GraphicsUnit.Pixel> è un membro del <xref:System.Drawing.GraphicsUnit> enumerazione, e <xref:System.Drawing.FontStyle.Regular> è un membro del <xref:System.Drawing.FontStyle> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a2591-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a2591-124">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a2591-124">Compiling the Code</span></span>  
 <span data-ttu-id="a2591-125">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="a2591-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2591-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2591-126">See also</span></span>
- [<span data-ttu-id="a2591-127">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="a2591-127">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [<span data-ttu-id="a2591-128">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="a2591-128">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
