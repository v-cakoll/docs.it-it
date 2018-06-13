---
title: 'Procedura: Data binding con un InkCanvas'
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 4081ae7dd6854934804062cfce60d10106c1e1d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543170"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a><span data-ttu-id="29ffd-102">Procedura: Data binding con un InkCanvas</span><span class="sxs-lookup"><span data-stu-id="29ffd-102">How to: Data Bind to an InkCanvas</span></span>
## <a name="example"></a><span data-ttu-id="29ffd-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="29ffd-103">Example</span></span>  
 <span data-ttu-id="29ffd-104">Nell'esempio seguente viene illustrato come associare il <xref:System.Windows.Controls.InkCanvas.Strokes%2A> proprietà di un <xref:System.Windows.Controls.InkCanvas> a un altro <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="29ffd-104">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property of an <xref:System.Windows.Controls.InkCanvas> to another <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 <span data-ttu-id="29ffd-105">Nell'esempio seguente viene illustrato come associare il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="29ffd-105">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property to a data source.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 <span data-ttu-id="29ffd-106">Nell'esempio seguente vengono dichiarati due <xref:System.Windows.Controls.InkCanvas> degli oggetti in XAML e stabilisce l'associazione dati tra queste e altre origini dati.</span><span class="sxs-lookup"><span data-stu-id="29ffd-106">The following example declares two <xref:System.Windows.Controls.InkCanvas> objects in XAML and establishes data binding between them and other data sources.</span></span>  <span data-ttu-id="29ffd-107">Il primo <xref:System.Windows.Controls.InkCanvas>, denominato `ic`, è associata a due origini dati.</span><span class="sxs-lookup"><span data-stu-id="29ffd-107">The first <xref:System.Windows.Controls.InkCanvas>, called `ic`, is bound to two data sources.</span></span>  <span data-ttu-id="29ffd-108">Il <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> e <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà `ic` sono associati a <xref:System.Windows.Controls.ListBox> oggetti, che a sua volta vengono associati alle matrici definite nel codice XAML.</span><span class="sxs-lookup"><span data-stu-id="29ffd-108">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> and <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties on `ic` are bound to <xref:System.Windows.Controls.ListBox> objects, which are in turn bound to arrays defined in the XAML.</span></span>  <span data-ttu-id="29ffd-109">Il <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, e <xref:System.Windows.Controls.InkCanvas.Strokes%2A> le proprietà del secondo <xref:System.Windows.Controls.InkCanvas> sono associati al primo <xref:System.Windows.Controls.InkCanvas>, `ic`.</span><span class="sxs-lookup"><span data-stu-id="29ffd-109">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, and <xref:System.Windows.Controls.InkCanvas.Strokes%2A> properties of the second <xref:System.Windows.Controls.InkCanvas> are bound to the first <xref:System.Windows.Controls.InkCanvas>, `ic`.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
