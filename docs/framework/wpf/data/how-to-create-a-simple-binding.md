---
title: 'Procedura: creare associazioni semplici'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a595f255b014e08b4b5b2036a7b1940e46df268f
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/22/2018
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="9b7b7-102">Procedura: creare associazioni semplici</span><span class="sxs-lookup"><span data-stu-id="9b7b7-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="9b7b7-103">In questo esempio viene illustrato come creare un semplice <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b7b7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b7b7-104">Example</span></span>  
 <span data-ttu-id="9b7b7-105">In questo esempio, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="9b7b7-106">Il `Person` oggetto viene definito nello spazio dei nomi denominato `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="9b7b7-107">La riga evidenziata che contiene il `<src>` elemento nell'esempio seguente viene creata un'istanza di `Person` dell'oggetto con un `PersonName` valore della proprietà `Joe`.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="9b7b7-108">Questa operazione viene eseguita `Resources` sezione e assegnare un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="9b7b7-109">La riga evidenziata che contiene il `<TextBlock>` elemento quindi associa la <xref:System.Windows.Controls.TextBlock> il controllo al `PersonName` proprietà.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="9b7b7-110">Di conseguenza, il <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".</span><span class="sxs-lookup"><span data-stu-id="9b7b7-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7b7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b7b7-111">See Also</span></span>  
 [<span data-ttu-id="9b7b7-112">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="9b7b7-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="9b7b7-113">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="9b7b7-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
