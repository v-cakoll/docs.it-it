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
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505113"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="4f2e4-102">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="4f2e4-102">Using Fonts and Text</span></span>
<span data-ttu-id="4f2e4-103">Sono disponibili diverse classi offerte da GDI+ e GDI per disegnare il testo in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-103">There are several classes offered by GDI+ and GDI for drawing text on Windows Forms.</span></span> <span data-ttu-id="4f2e4-104">GDI+ <xref:System.Drawing.Graphics> classe dispone di numerose <xref:System.Drawing.Graphics.DrawString%2A> metodi che consentono di specificare diverse caratteristiche del testo, ad esempio percorso, rettangolo, tipo di carattere e il formato di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-104">The GDI+ <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="4f2e4-105">Inoltre, è possibile disegnare e misurare il testo con GDI usando il metodo statico <xref:System.Windows.Forms.TextRenderer.DrawText%2A> e <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> metodi offerti dal `TextRenderer` classe.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-105">In addition, you can draw and measure text with GDI using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="4f2e4-106">I metodi GDI consentono anche di specificare posizione, tipo di carattere e il formato.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-106">The GDI methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="4f2e4-107">È possibile scegliere GDI o GDI+ per il rendering del testo; Tuttavia, GDI offre in genere prestazioni migliori e la misurazione del testo più accurate.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-107">You can choose either GDI or GDI+ for text rendering; however, GDI generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="4f2e4-108">Le altre classi che contribuiscono al rendering del testo `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, e `TextFormatFlags`.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f2e4-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4f2e4-109">In This Section</span></span>  
 [<span data-ttu-id="4f2e4-110">Procedura: Costruire i tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="4f2e4-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="4f2e4-111">Viene illustrato come creare `Font` e `FontFamily` oggetti.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="4f2e4-112">Procedura: Disegnare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="4f2e4-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="4f2e4-113">Viene descritto come disegnare testo in una determinata posizione con GDI+ e GDI.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-113">Describes how to draw text in a certain location using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="4f2e4-114">Procedura: Disegnare testo sottoposto a wrapping in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="4f2e4-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="4f2e4-115">Illustra come disegnare testo in un rettangolo con GDI+ e GDI.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-115">Explains how to draw text in a rectangle using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="4f2e4-116">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="4f2e4-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="4f2e4-117">Viene illustrato come utilizzare GDI per disegnare il testo.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-117">Demonstrates how to use GDI for drawing text.</span></span>  
  
 [<span data-ttu-id="4f2e4-118">Procedura: Allineare il testo creato</span><span class="sxs-lookup"><span data-stu-id="4f2e4-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="4f2e4-119">Viene illustrato come formattare il testo di GDI+ e GDI.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-119">Shows how to format GDI+ and GDI text.</span></span>  
  
 [<span data-ttu-id="4f2e4-120">Procedura: Creare testo verticale</span><span class="sxs-lookup"><span data-stu-id="4f2e4-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="4f2e4-121">Viene descritto come disegnare il testo allineato in senso verticale con GDI+.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-121">Describes how to draw vertically aligned text with GDI+.</span></span>  
  
 [<span data-ttu-id="4f2e4-122">Procedura: Impostare punti di tabulazione nel testo disegnato</span><span class="sxs-lookup"><span data-stu-id="4f2e4-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="4f2e4-123">Viene illustrato come disegnare il testo con le tabulazioni con GDI+.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-123">Shows how draw text with tab stops with GDI+.</span></span>  
  
 [<span data-ttu-id="4f2e4-124">Procedura: Enumerare i tipi di carattere installati</span><span class="sxs-lookup"><span data-stu-id="4f2e4-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="4f2e4-125">Viene illustrato come elencare i nomi dei tipi di carattere installati.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="4f2e4-126">Procedura: Creare una raccolta di caratteri privata</span><span class="sxs-lookup"><span data-stu-id="4f2e4-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="4f2e4-127">Viene descritto come creare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="4f2e4-128">Procedura: Ottenere le metriche del tipo di carattere</span><span class="sxs-lookup"><span data-stu-id="4f2e4-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="4f2e4-129">Viene illustrato come ottenere le metriche del tipo di carattere, ad esempio ascent di cella e dei valori descent con.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="4f2e4-130">Procedura: Usare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="4f2e4-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="4f2e4-131">Viene illustrato come utilizzare l'anti-aliasing durante il disegno di testo.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4f2e4-132">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="4f2e4-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="4f2e4-133">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="4f2e4-134">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="4f2e4-135">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="4f2e4-136">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="4f2e4-137">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4f2e4-137">Describes this class and contains links to all of its members.</span></span>
