---
title: Utilizzo di tipi di carattere e testo
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: d157b51e24009d847dede9ea6a9f81c8898c5b06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526263"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="4cc67-102">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="4cc67-102">Using Fonts and Text</span></span>
<span data-ttu-id="4cc67-103">Sono disponibili diverse classi offerto da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] per il disegno di testo in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="4cc67-103">There are several classes offered by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text on Windows Forms.</span></span> <span data-ttu-id="4cc67-104">Il [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> classe dispone di numerosi <xref:System.Drawing.Graphics.DrawString%2A> metodi che consentono di specificare varie funzionalità di testo, ad esempio percorso, formato, carattere e rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="4cc67-104">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="4cc67-105">Inoltre, è possibile disegnare e misurare il testo con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mediante il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> e <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> metodi offerti dalla `TextRenderer` classe.</span><span class="sxs-lookup"><span data-stu-id="4cc67-105">In addition, you can draw and measure text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="4cc67-106">Il [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] metodi consentono anche di specificare il percorso, tipo di carattere e formato.</span><span class="sxs-lookup"><span data-stu-id="4cc67-106">The [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="4cc67-107">È possibile scegliere una [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] o [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per il rendering del testo; tuttavia, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] in genere offre migliori prestazioni e la misurazione più accurata di testo.</span><span class="sxs-lookup"><span data-stu-id="4cc67-107">You can choose either [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] or [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] for text rendering; however, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="4cc67-108">Le altre classi che contribuiscono al rendering del testo `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, e `TextFormatFlags`.</span><span class="sxs-lookup"><span data-stu-id="4cc67-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4cc67-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4cc67-109">In This Section</span></span>  
 [<span data-ttu-id="4cc67-110">Procedura: Creare caratteri e gruppi di caratteri</span><span class="sxs-lookup"><span data-stu-id="4cc67-110">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="4cc67-111">Viene illustrato come creare `Font` e `FontFamily` oggetti.</span><span class="sxs-lookup"><span data-stu-id="4cc67-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="4cc67-112">Procedura: Creare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="4cc67-112">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="4cc67-113">Viene descritto come disegnare testo in una determinata posizione utilizzando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc67-113">Describes how to draw text in a certain location using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="4cc67-114">Procedura: Creare testo disposto su più righe in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="4cc67-114">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="4cc67-115">Illustra come disegnare il testo in un rettangolo utilizzando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc67-115">Explains how to draw text in a rectangle using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="4cc67-116">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="4cc67-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="4cc67-117">Viene illustrato come utilizzare [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] per il disegno di testo.</span><span class="sxs-lookup"><span data-stu-id="4cc67-117">Demonstrates how to use [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text.</span></span>  
  
 [<span data-ttu-id="4cc67-118">Procedura: Allineare il testo creato</span><span class="sxs-lookup"><span data-stu-id="4cc67-118">How to: Align Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 <span data-ttu-id="4cc67-119">Viene illustrato come formattare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] testo.</span><span class="sxs-lookup"><span data-stu-id="4cc67-119">Shows how to format [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] text.</span></span>  
  
 [<span data-ttu-id="4cc67-120">Procedura: Creare testo verticale</span><span class="sxs-lookup"><span data-stu-id="4cc67-120">How to: Create Vertical Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 <span data-ttu-id="4cc67-121">Viene descritto come disegnare il testo allineato verticalmente con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc67-121">Describes how to draw vertically aligned text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="4cc67-122">Procedura: Impostare punti di tabulazione nel testo disegnato</span><span class="sxs-lookup"><span data-stu-id="4cc67-122">How to: Set Tab Stops in Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="4cc67-123">Viene illustrato come disegnare testo con tabulazioni con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc67-123">Shows how draw text with tab stops with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="4cc67-124">Procedura: Enumerare i tipi di carattere installati</span><span class="sxs-lookup"><span data-stu-id="4cc67-124">How to: Enumerate Installed Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="4cc67-125">Viene illustrato come elencare i nomi dei tipi di carattere installati.</span><span class="sxs-lookup"><span data-stu-id="4cc67-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="4cc67-126">Procedura: Creare una raccolta di caratteri privata</span><span class="sxs-lookup"><span data-stu-id="4cc67-126">How to: Create a Private Font Collection</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="4cc67-127">Viene descritto come creare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4cc67-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="4cc67-128">Procedura: Recuperare i criteri di misurazione dei caratteri</span><span class="sxs-lookup"><span data-stu-id="4cc67-128">How to: Obtain Font Metrics</span></span>](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 <span data-ttu-id="4cc67-129">Viene illustrato come ottenere la metrica di tipo di carattere, ad esempio ascent di cella e dei valori descent con.</span><span class="sxs-lookup"><span data-stu-id="4cc67-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="4cc67-130">Procedura: Usare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="4cc67-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="4cc67-131">Viene illustrato come utilizzare l'anti-aliasing durante il disegno di testo.</span><span class="sxs-lookup"><span data-stu-id="4cc67-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4cc67-132">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="4cc67-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="4cc67-133">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4cc67-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="4cc67-134">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4cc67-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="4cc67-135">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4cc67-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="4cc67-136">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4cc67-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="4cc67-137">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4cc67-137">Describes this class and contains links to all of its members.</span></span>
