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
ms.openlocfilehash: c9fe16752223203806c7d3828f632aad0cab0c28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769420"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="7d1ec-102">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="7d1ec-102">Using Fonts and Text</span></span>
<span data-ttu-id="7d1ec-103">Sono disponibili diverse classi offerte dal [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] per disegnare il testo in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-103">There are several classes offered by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text on Windows Forms.</span></span> <span data-ttu-id="7d1ec-104">Il [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> classe dispone di numerose <xref:System.Drawing.Graphics.DrawString%2A> metodi che consentono di specificare diverse caratteristiche del testo, ad esempio percorso, rettangolo, tipo di carattere e il formato di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-104">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="7d1ec-105">Inoltre, è possibile disegnare e misurare il testo con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] usando il metodo statico <xref:System.Windows.Forms.TextRenderer.DrawText%2A> e <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> metodi offerti dal `TextRenderer` classe.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-105">In addition, you can draw and measure text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="7d1ec-106">Il [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] metodi consentono anche di specificare posizione, tipo di carattere e il formato.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-106">The [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="7d1ec-107">È possibile scegliere [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] oppure [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per il rendering del testo; tuttavia, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] in genere offre migliori prestazioni e la misurazione del testo più accurate.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-107">You can choose either [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] or [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] for text rendering; however, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="7d1ec-108">Le altre classi che contribuiscono al rendering del testo `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, e `TextFormatFlags`.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d1ec-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="7d1ec-109">In This Section</span></span>  
 [<span data-ttu-id="7d1ec-110">Procedura: Costruire i tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="7d1ec-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="7d1ec-111">Viene illustrato come creare `Font` e `FontFamily` oggetti.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="7d1ec-112">Procedura: Disegnare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="7d1ec-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="7d1ec-113">Descrive come disegnare testo in una determinata posizione utilizzando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1ec-113">Describes how to draw text in a certain location using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="7d1ec-114">Procedura: Disegnare testo sottoposto a wrapping in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="7d1ec-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="7d1ec-115">Illustra come disegnare il testo in un rettangolo utilizzando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1ec-115">Explains how to draw text in a rectangle using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="7d1ec-116">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="7d1ec-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="7d1ec-117">Viene illustrato come utilizzare [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] per disegnare il testo.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-117">Demonstrates how to use [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text.</span></span>  
  
 [<span data-ttu-id="7d1ec-118">Procedura: Allineare il testo creato</span><span class="sxs-lookup"><span data-stu-id="7d1ec-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="7d1ec-119">Viene illustrato come formattare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] testo.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-119">Shows how to format [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] text.</span></span>  
  
 [<span data-ttu-id="7d1ec-120">Procedura: Creare testo verticale</span><span class="sxs-lookup"><span data-stu-id="7d1ec-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="7d1ec-121">Viene descritto come disegnare il testo allineato in senso verticale con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1ec-121">Describes how to draw vertically aligned text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="7d1ec-122">Procedura: Impostare punti di tabulazione nel testo disegnato</span><span class="sxs-lookup"><span data-stu-id="7d1ec-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="7d1ec-123">Viene illustrato come disegnare il testo con le tabulazioni con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1ec-123">Shows how draw text with tab stops with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="7d1ec-124">Procedura: Enumerare i tipi di carattere installati</span><span class="sxs-lookup"><span data-stu-id="7d1ec-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="7d1ec-125">Viene illustrato come elencare i nomi dei tipi di carattere installati.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="7d1ec-126">Procedura: Creare una raccolta di caratteri privata</span><span class="sxs-lookup"><span data-stu-id="7d1ec-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="7d1ec-127">Viene descritto come creare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="7d1ec-128">Procedura: Ottenere le metriche del tipo di carattere</span><span class="sxs-lookup"><span data-stu-id="7d1ec-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="7d1ec-129">Viene illustrato come ottenere le metriche del tipo di carattere, ad esempio ascent di cella e dei valori descent con.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="7d1ec-130">Procedura: Usare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="7d1ec-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="7d1ec-131">Viene illustrato come utilizzare l'anti-aliasing durante il disegno di testo.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7d1ec-132">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="7d1ec-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="7d1ec-133">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="7d1ec-134">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="7d1ec-135">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="7d1ec-136">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="7d1ec-137">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="7d1ec-137">Describes this class and contains links to all of its members.</span></span>
