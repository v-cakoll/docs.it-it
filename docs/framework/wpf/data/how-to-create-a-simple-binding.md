---
title: 'Procedura: creare associazioni semplici'
description: Consente di creare un binding semplice per le applicazioni tramite questo esempio di procedura in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 63dc44b442bb4658382bf12faf57b51c8e0698bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618701"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="d8dd7-103">Procedura: creare associazioni semplici</span><span class="sxs-lookup"><span data-stu-id="d8dd7-103">How to: Create a Simple Binding</span></span>
<span data-ttu-id="d8dd7-104">Questo esempio illustra come creare un semplice <xref:System.Windows.Data.Binding> .</span><span class="sxs-lookup"><span data-stu-id="d8dd7-104">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8dd7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8dd7-105">Example</span></span>  
 <span data-ttu-id="d8dd7-106">In questo esempio è presente un `Person` oggetto con una proprietà stringa denominata `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="d8dd7-106">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="d8dd7-107">L' `Person` oggetto è definito nello spazio dei nomi denominato `SDKSample` .</span><span class="sxs-lookup"><span data-stu-id="d8dd7-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="d8dd7-108">La riga evidenziata che contiene l' `<src>` elemento nell'esempio seguente crea un'istanza dell' `Person` oggetto con un `PersonName` valore della proprietà `Joe` .</span><span class="sxs-lookup"><span data-stu-id="d8dd7-108">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="d8dd7-109">Questa operazione viene eseguita nella `Resources` sezione ed è stata assegnata una `x:Key` .</span><span class="sxs-lookup"><span data-stu-id="d8dd7-109">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="d8dd7-110">La riga evidenziata che contiene l' `<TextBlock>` elemento associa quindi il <xref:System.Windows.Controls.TextBlock> controllo alla `PersonName` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="d8dd7-110">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="d8dd7-111">Di conseguenza, <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".</span><span class="sxs-lookup"><span data-stu-id="d8dd7-111">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8dd7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8dd7-112">See also</span></span>

- [<span data-ttu-id="d8dd7-113">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="d8dd7-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="d8dd7-114">Procedure</span><span class="sxs-lookup"><span data-stu-id="d8dd7-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
