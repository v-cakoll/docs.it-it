---
title: Creare testo utilizzando i glifi
ms.date: 03/30/2017
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
ms.openlocfilehash: 55bbc50de519d6607a843fcd633f2c07db53109f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141674"
---
# <a name="draw-text-using-glyphs"></a><span data-ttu-id="3e409-102">Creare testo utilizzando i glifi</span><span class="sxs-lookup"><span data-stu-id="3e409-102">Draw Text Using Glyphs</span></span>
<span data-ttu-id="3e409-103">In questo argomento illustra come usare il livello basso <xref:System.Windows.Documents.Glyphs> oggetto per la visualizzazione testo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e409-103">This topic explains how to use the low-level <xref:System.Windows.Documents.Glyphs> object to display text in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e409-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e409-104">Example</span></span>  
 <span data-ttu-id="3e409-105">Gli esempi seguenti illustrano come definire le proprietà per un <xref:System.Windows.Documents.Glyphs> dell'oggetto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e409-105">The following examples show how to define properties for a <xref:System.Windows.Documents.Glyphs> object in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="3e409-106">Il <xref:System.Windows.Documents.Glyphs> oggetto rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e409-106">The <xref:System.Windows.Documents.Glyphs> object represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="3e409-107">Negli esempi si presuppone che i tipi di carattere Arial, Courier New e Times New Roman siano installati nella cartella C:\WINDOWS\Fonts nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="3e409-107">The examples assume that the Arial, Courier New, and Times New Roman fonts are installed in the C:\WINDOWS\Fonts folder on the local computer.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="3e409-108">In questo esempio viene illustrato come definire altre proprietà degli <xref:System.Windows.Documents.Glyphs> oggetti [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e409-108">This example shows how to define other properties of <xref:System.Windows.Documents.Glyphs> objects in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3e409-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e409-109">See also</span></span>

- [<span data-ttu-id="3e409-110">Funzionalità tipografiche di WPF</span><span class="sxs-lookup"><span data-stu-id="3e409-110">Typography in WPF</span></span>](typography-in-wpf.md)
