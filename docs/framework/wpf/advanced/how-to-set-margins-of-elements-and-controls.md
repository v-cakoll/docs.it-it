---
title: 'Procedura: Impostare i margini di elementi e controlli'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
ms.openlocfilehash: 3263810806b6b4bbec15eadfd1f1da3a57d12698
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356273"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a><span data-ttu-id="d71d3-102">Procedura: Impostare i margini di elementi e controlli</span><span class="sxs-lookup"><span data-stu-id="d71d3-102">How to: Set Margins of Elements and Controls</span></span>
<span data-ttu-id="d71d3-103">In questo esempio viene descritto come impostare il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà, modificando i valori di proprietà esistenti per il margine nel code-behind.</span><span class="sxs-lookup"><span data-stu-id="d71d3-103">This example describes how to set the <xref:System.Windows.FrameworkElement.Margin%2A> property, by changing any existing property value for the margin in code-behind.</span></span> <span data-ttu-id="d71d3-104">Il <xref:System.Windows.FrameworkElement.Margin%2A> è una proprietà della <xref:System.Windows.FrameworkElement> elemento di base e pertanto viene ereditata da un'ampia gamma di controlli e altri elementi.</span><span class="sxs-lookup"><span data-stu-id="d71d3-104">The <xref:System.Windows.FrameworkElement.Margin%2A> property is a property of the <xref:System.Windows.FrameworkElement> base element, and is thus inherited by a variety of controls and other elements.</span></span>  
  
 <span data-ttu-id="d71d3-105">In questo esempio è scritto in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], con un code-behind del file che il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] fa riferimento a.</span><span class="sxs-lookup"><span data-stu-id="d71d3-105">This example is written in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], with a code-behind file that the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] refers to.</span></span> <span data-ttu-id="d71d3-106">Il code-behind viene visualizzato sia in un C# e una versione di Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d71d3-106">The code-behind is shown in both a C# and a Microsoft Visual Basic version.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d71d3-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="d71d3-107">Example</span></span>  
 [!code-xaml[FEMarginProgrammatic#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
