---
title: "Procedura: Ruotare l'input penna"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], rotating
- rotating ink [WPF]
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
ms.openlocfilehash: 31f5d0ffb6f0fdcdaef13bc44653f8c7938ac7f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768459"
---
# <a name="how-to-rotate-ink"></a><span data-ttu-id="ba8d6-102">Procedura: Ruotare l'input penna</span><span class="sxs-lookup"><span data-stu-id="ba8d6-102">How to: Rotate Ink</span></span>
## <a name="example"></a><span data-ttu-id="ba8d6-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba8d6-103">Example</span></span>  
 <span data-ttu-id="ba8d6-104">Nell'esempio seguente consente di copiare l'input penna da un <xref:System.Windows.Controls.InkCanvas> a un <xref:System.Windows.Controls.Canvas> che contiene un <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="ba8d6-104">The following example copies the ink from an <xref:System.Windows.Controls.InkCanvas> to a <xref:System.Windows.Controls.Canvas> that contains an <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="ba8d6-105">Quando l'applicazione input penna viene copiato, anche ruotato di 90 gradi in senso orario.</span><span class="sxs-lookup"><span data-stu-id="ba8d6-105">When the application copies the ink, it also rotates the ink 90 degrees clockwise.</span></span>  
  
 [!code-xaml[HowToRotateInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="ba8d6-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba8d6-106">Example</span></span>  
 <span data-ttu-id="ba8d6-107">L'esempio seguente è una classe personalizzata <xref:System.Windows.Documents.Adorner> che consente di ruotare i tratti su un <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="ba8d6-107">The following example is a custom <xref:System.Windows.Documents.Adorner> that rotates the strokes on an <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[AdornerForStrokes#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 <span data-ttu-id="ba8d6-108">L'esempio seguente è un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file che definisce un <xref:System.Windows.Controls.InkPresenter> e popolarla con input penna.</span><span class="sxs-lookup"><span data-stu-id="ba8d6-108">The following example is a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that defines an <xref:System.Windows.Controls.InkPresenter> and populates it with ink.</span></span> <span data-ttu-id="ba8d6-109">Il `Window_Loaded` gestore dell'evento aggiunge lo strumento decorativo personalizzato per il <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="ba8d6-109">The `Window_Loaded` event handler adds the custom adorner to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-xaml[AdornerForStrokes#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]
