---
title: Creare testo utilizzando i glifi
ms.date: 03/30/2017
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
ms.openlocfilehash: e2b35eb6df140551d5db7d597826df53e37182fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542526"
---
# <a name="draw-text-using-glyphs"></a><span data-ttu-id="97893-102">Creare testo utilizzando i glifi</span><span class="sxs-lookup"><span data-stu-id="97893-102">Draw Text Using Glyphs</span></span>
<span data-ttu-id="97893-103">In questo argomento viene illustrato come utilizzare di basso livello <xref:System.Windows.Documents.Glyphs> oggetto per visualizzare il testo in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97893-103">This topic explains how to use the low-level <xref:System.Windows.Documents.Glyphs> object to display text in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="97893-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="97893-104">Example</span></span>  
 <span data-ttu-id="97893-105">Negli esempi seguenti viene illustrano come definire le proprietà per un <xref:System.Windows.Documents.Glyphs> oggetto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97893-105">The following examples show how to define properties for a <xref:System.Windows.Documents.Glyphs> object in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="97893-106">Il <xref:System.Windows.Documents.Glyphs> oggetto rappresenta l'output di un <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97893-106">The <xref:System.Windows.Documents.Glyphs> object represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="97893-107">Negli esempi si presuppone che i tipi di carattere Arial, Courier New e Times New Roman siano installati nella cartella C:\WINDOWS\Fonts nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="97893-107">The examples assume that the Arial, Courier New, and Times New Roman fonts are installed in the C:\WINDOWS\Fonts folder on the local computer.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="97893-108">In questo esempio viene illustrato come definire altre proprietà di <xref:System.Windows.Documents.Glyphs> oggetti [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97893-108">This example shows how to define other properties of <xref:System.Windows.Documents.Glyphs> objects in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="97893-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97893-109">See Also</span></span>  
 [<span data-ttu-id="97893-110">Funzionalità tipografiche di WPF</span><span class="sxs-lookup"><span data-stu-id="97893-110">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)
