---
title: 'Procedura: disegnare un''area con un colore a tinta unita'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a5fe948c3cc6088f238f1f8f53c26c5f1fa5b2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="19906-102">Procedura: disegnare un'area con un colore a tinta unita</span><span class="sxs-lookup"><span data-stu-id="19906-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="19906-103">Per disegnare un'area con un colore a tinta unita, è possibile utilizzare un pennello di sistema predefinito, ad esempio <xref:System.Windows.Media.Brushes.Red%2A> o <xref:System.Windows.Media.Brushes.Blue%2A>, oppure è possibile creare un nuovo <xref:System.Windows.Media.SolidColorBrush> e una descrizione relativa <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizzando i valori alfa, rossi, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="19906-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="19906-104">In XAML è anche possibile disegnare un'area con un colore a tinta unita usando la notazione esadecimale.</span><span class="sxs-lookup"><span data-stu-id="19906-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="19906-105">Negli esempi seguenti viene utilizzata ognuna di queste tecniche per disegnare un <xref:System.Windows.Shapes.Rectangle> blu.</span><span class="sxs-lookup"><span data-stu-id="19906-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19906-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="19906-106">Example</span></span>  
 <span data-ttu-id="19906-107">**Uso di un pennello predefinito**</span><span class="sxs-lookup"><span data-stu-id="19906-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="19906-108">Nell'esempio seguente viene utilizzato il pennello predefinito <xref:System.Windows.Media.Brushes.Blue%2A> per disegnare un rettangolo blu.</span><span class="sxs-lookup"><span data-stu-id="19906-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="19906-109">**Uso della notazione esadecimale**</span><span class="sxs-lookup"><span data-stu-id="19906-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="19906-110">L'esempio successivo usa la notazione esadecimale a 8 cifre per disegnare un rettangolo blu.</span><span class="sxs-lookup"><span data-stu-id="19906-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="19906-111">**Uso dei valori ARGB**</span><span class="sxs-lookup"><span data-stu-id="19906-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="19906-112">Nell'esempio successivo viene creato un <xref:System.Windows.Media.SolidColorBrush> e descrive il <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizzando i valori ARGB per il colore blu.</span><span class="sxs-lookup"><span data-stu-id="19906-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="19906-113">Per altre modalità di descrizione del colore, vedere il <xref:System.Windows.Media.Color> struttura.</span><span class="sxs-lookup"><span data-stu-id="19906-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="19906-114">**Argomenti correlati**</span><span class="sxs-lookup"><span data-stu-id="19906-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="19906-115">Per ulteriori informazioni su <xref:System.Windows.Media.SolidColorBrush> e ulteriori esempi, vedere il [disegni con colori a tinta unita e sfumature Panoramica](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) Panoramica.</span><span class="sxs-lookup"><span data-stu-id="19906-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="19906-116">Questo esempio di codice fa parte di un esempio più esaustivo disponibile per la <xref:System.Windows.Media.SolidColorBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="19906-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="19906-117">Per l'esempio completo, vedere [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli).</span><span class="sxs-lookup"><span data-stu-id="19906-117">For the complete sample, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19906-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19906-118">See Also</span></span>  
 <xref:System.Windows.Media.Brushes>
