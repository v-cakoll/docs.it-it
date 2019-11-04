---
title: 'Procedura: creare associazioni semplici'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453505"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="09f7d-102">Procedura: creare associazioni semplici</span><span class="sxs-lookup"><span data-stu-id="09f7d-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="09f7d-103">Questo esempio illustra come creare una semplice <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="09f7d-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09f7d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="09f7d-104">Example</span></span>  
 <span data-ttu-id="09f7d-105">In questo esempio è presente un oggetto `Person` con una proprietà stringa denominata `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="09f7d-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="09f7d-106">L'oggetto `Person` viene definito nello spazio dei nomi denominato `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="09f7d-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="09f7d-107">La riga evidenziata che contiene l'elemento `<src>` nell'esempio seguente crea un'istanza dell'oggetto `Person` con un valore della proprietà `PersonName` di `Joe`.</span><span class="sxs-lookup"><span data-stu-id="09f7d-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="09f7d-108">Questa operazione viene eseguita nella sezione `Resources` e assegnata una `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="09f7d-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="09f7d-109">La riga evidenziata che contiene l'elemento `<TextBlock>` associa quindi il controllo <xref:System.Windows.Controls.TextBlock> alla proprietà `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="09f7d-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="09f7d-110">Di conseguenza, il <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".</span><span class="sxs-lookup"><span data-stu-id="09f7d-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f7d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09f7d-111">See also</span></span>

- [<span data-ttu-id="09f7d-112">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="09f7d-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="09f7d-113">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="09f7d-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
