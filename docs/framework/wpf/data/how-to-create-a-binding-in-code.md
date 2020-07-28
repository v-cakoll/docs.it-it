---
title: 'Procedura: creare associazioni nel codice'
description: Informazioni su come creare un'associazione nel codice in un'applicazione Windows Presentation Foundation chiamando direttamente il metodo SetBinding.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: aa2a29f4c1262d8ac54641b856c297b284b23a38
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165812"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="e362f-103">Procedura: creare associazioni nel codice</span><span class="sxs-lookup"><span data-stu-id="e362f-103">How to: Create a Binding in Code</span></span>
<span data-ttu-id="e362f-104">Questo esempio illustra come creare e impostare un oggetto <xref:System.Windows.Data.Binding> nel codice.</span><span class="sxs-lookup"><span data-stu-id="e362f-104">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e362f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e362f-105">Example</span></span>  
 <span data-ttu-id="e362f-106">La <xref:System.Windows.FrameworkElement> classe e la <xref:System.Windows.FrameworkContentElement> classe espongono entrambi un `SetBinding` metodo.</span><span class="sxs-lookup"><span data-stu-id="e362f-106">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="e362f-107">Se si associa un elemento che eredita una di queste classi, è possibile chiamare direttamente il <xref:System.Windows.FrameworkElement.SetBinding%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e362f-107">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="e362f-108">Nell'esempio seguente viene creata una classe denominata, `MyData` , che contiene una proprietà denominata `MyDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="e362f-108">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="e362f-109">Nell'esempio seguente viene illustrato come creare un oggetto Binding per impostare l'origine dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="e362f-109">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="e362f-110">Nell'esempio viene usato <xref:System.Windows.FrameworkElement.SetBinding%2A> per associare la <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà di `myText` , che è un <xref:System.Windows.Controls.TextBlock> controllo, a `MyDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="e362f-110">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="e362f-111">Per l'esempio di codice completo, vedere [esempio di associazione di solo codice](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="e362f-111">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="e362f-112">Anziché chiamare <xref:System.Windows.FrameworkElement.SetBinding%2A> , è possibile usare il <xref:System.Windows.Data.BindingOperations.SetBinding%2A> metodo statico della <xref:System.Windows.Data.BindingOperations> classe.</span><span class="sxs-lookup"><span data-stu-id="e362f-112">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="e362f-113">Nell'esempio seguente viene chiamato il comando <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> anziché <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> per eseguire l'associazione `myText` a `myDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="e362f-113">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="e362f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e362f-114">See also</span></span>

- [<span data-ttu-id="e362f-115">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="e362f-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="e362f-116">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="e362f-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
