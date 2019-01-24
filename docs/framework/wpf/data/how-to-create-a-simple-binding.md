---
title: "Procedura: Creare un'associazione semplice"
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 3e38fa5fd1c7d0a635efd93de6ebe551f1eb1b82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594837"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="bfe19-102">Procedura: Creare un'associazione semplice</span><span class="sxs-lookup"><span data-stu-id="bfe19-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="bfe19-103">In questo esempio illustra come creare una semplice <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="bfe19-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfe19-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bfe19-104">Example</span></span>  
 <span data-ttu-id="bfe19-105">In questo esempio, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="bfe19-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="bfe19-106">Il `Person` oggetto viene definito nello spazio dei nomi denominato `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="bfe19-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="bfe19-107">La riga evidenziata che contiene il `<src>` elemento nell'esempio seguente crea un'istanza di `Person` dell'oggetto con un `PersonName` valore della proprietà `Joe`.</span><span class="sxs-lookup"><span data-stu-id="bfe19-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="bfe19-108">Questa operazione viene eseguita `Resources` sezione e assegnare un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="bfe19-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="bfe19-109">La riga evidenziata che contiene il `<TextBlock>` elemento associa quindi il <xref:System.Windows.Controls.TextBlock> controllo il `PersonName` proprietà.</span><span class="sxs-lookup"><span data-stu-id="bfe19-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="bfe19-110">Di conseguenza, il <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".</span><span class="sxs-lookup"><span data-stu-id="bfe19-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe19-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe19-111">See also</span></span>
- [<span data-ttu-id="bfe19-112">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="bfe19-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="bfe19-113">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="bfe19-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
