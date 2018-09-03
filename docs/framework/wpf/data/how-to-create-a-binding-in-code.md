---
title: 'Procedura: creare associazioni nel codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 2d13650cb3e9a4e97a6642992b7211f323b9ea96
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483021"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="79436-102">Procedura: creare associazioni nel codice</span><span class="sxs-lookup"><span data-stu-id="79436-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="79436-103">Questo esempio illustra come creare e impostare un <xref:System.Windows.Data.Binding> nel codice.</span><span class="sxs-lookup"><span data-stu-id="79436-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79436-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="79436-104">Example</span></span>  
 <span data-ttu-id="79436-105">Il <xref:System.Windows.FrameworkElement> classe e il <xref:System.Windows.FrameworkContentElement> classe espongono entrambi una `SetBinding` (metodo).</span><span class="sxs-lookup"><span data-stu-id="79436-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="79436-106">Se si associa un elemento che eredita da una di queste classi, è possibile chiamare il <xref:System.Windows.FrameworkElement.SetBinding%2A> direttamente al metodo.</span><span class="sxs-lookup"><span data-stu-id="79436-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="79436-107">L'esempio seguente crea una classe denominata `MyData`, che contiene una proprietà denominata `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="79436-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="79436-108">Nell'esempio seguente viene illustrato come creare un oggetto di associazione per impostare l'origine dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="79436-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="79436-109">Nell'esempio viene usato <xref:System.Windows.FrameworkElement.SetBinding%2A> per associare il <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà di `myText`, che è un <xref:System.Windows.Controls.TextBlock> a controllare `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="79436-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="79436-110">Per l'esempio di codice completo, vedere [esempio di associazione di solo codice](https://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).</span><span class="sxs-lookup"><span data-stu-id="79436-110">For the complete code sample, see [Code-only Binding Sample](https://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).</span></span>  
  
 <span data-ttu-id="79436-111">Invece di chiamare <xref:System.Windows.FrameworkElement.SetBinding%2A>, è possibile usare il <xref:System.Windows.Data.BindingOperations.SetBinding%2A> metodo statico del <xref:System.Windows.Data.BindingOperations> classe.</span><span class="sxs-lookup"><span data-stu-id="79436-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="79436-112">L'esempio seguente, le chiamate <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> invece di <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> associare `myText` a `myDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="79436-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="79436-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79436-113">See Also</span></span>  
 [<span data-ttu-id="79436-114">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="79436-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="79436-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="79436-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
