---
title: 'Procedura: creare associazioni semplici'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a61844f917539f5d5e7c99299c8a33f4aa18450f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="098b6-102">Procedura: creare associazioni semplici</span><span class="sxs-lookup"><span data-stu-id="098b6-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="098b6-103">In questo esempio viene illustrato come creare un semplice <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="098b6-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="098b6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="098b6-104">Example</span></span>  
 <span data-ttu-id="098b6-105">In questo esempio, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="098b6-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="098b6-106">Il `Person` oggetto viene definito nello spazio dei nomi denominato `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="098b6-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="098b6-107">Nell'esempio seguente viene creata un'istanza di `Person` dell'oggetto con un `PersonName` valore della proprietà `Joe`.</span><span class="sxs-lookup"><span data-stu-id="098b6-107">The following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="098b6-108">Questa operazione viene eseguita `Resources` sezione e assegnare un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="098b6-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xaml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 <span data-ttu-id="098b6-109">Per associare il `PersonName` è necessario effettuare le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="098b6-109">To bind to the `PersonName` property you would do the following:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="098b6-110">Di conseguenza, il <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".</span><span class="sxs-lookup"><span data-stu-id="098b6-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="098b6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="098b6-111">See Also</span></span>  
 [<span data-ttu-id="098b6-112">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="098b6-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="098b6-113">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="098b6-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
