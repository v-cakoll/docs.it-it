---
title: "Procedura: Eseguire l'associazione a un'enumerazione"
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: df26d2bd08e4691837f739a4e71d3bb1a25bdd00
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377794"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="58a48-102">Procedura: Eseguire l'associazione a un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="58a48-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="58a48-103">In questo esempio viene illustrato come eseguire l'associazione a un'enumerazione tramite l'associazione al metodo GetValues dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="58a48-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58a48-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="58a48-104">Example</span></span>  
 <span data-ttu-id="58a48-105">Nell'esempio seguente, il <xref:System.Windows.Controls.ListBox> Visualizza l'elenco di <xref:System.Windows.HorizontalAlignment> valori di enumerazione tramite associazione dati.</span><span class="sxs-lookup"><span data-stu-id="58a48-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="58a48-106">Il <xref:System.Windows.Controls.ListBox> e il <xref:System.Windows.Controls.Button> sono associati in modo che sia possibile modificare le <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore della proprietà il <xref:System.Windows.Controls.Button> selezionando un valore nel <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="58a48-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="58a48-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58a48-107">See also</span></span>
- [<span data-ttu-id="58a48-108">Eseguire l'associazione a un metodo</span><span class="sxs-lookup"><span data-stu-id="58a48-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="58a48-109">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="58a48-109">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="58a48-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="58a48-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
