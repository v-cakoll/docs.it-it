---
title: 'Procedura: posizionare gli elementi figlio di una griglia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186715"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="4e4ca-102">Procedura: posizionare gli elementi figlio di una griglia</span><span class="sxs-lookup"><span data-stu-id="4e4ca-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="4e4ca-103">In questo esempio viene illustrato come utilizzare i <xref:System.Windows.Controls.Grid> metodi get e set definiti per posizionare gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="4e4ca-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e4ca-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e4ca-104">Example</span></span>  
 <span data-ttu-id="4e4ca-105">Nell'esempio seguente viene <xref:System.Windows.Controls.Grid> definito`grid1`un elemento padre ( ) con tre colonne e tre righe.</span><span class="sxs-lookup"><span data-stu-id="4e4ca-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="4e4ca-106">Un <xref:System.Windows.Shapes.Rectangle> elemento`rect1`figlio ( ) <xref:System.Windows.Controls.Grid> viene aggiunto alla posizione in colonna zero, la posizione della riga zero.</span><span class="sxs-lookup"><span data-stu-id="4e4ca-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="4e4ca-107"><xref:System.Windows.Controls.Button>gli elementi rappresentano metodi che possono <xref:System.Windows.Shapes.Rectangle> essere <xref:System.Windows.Controls.Grid>chiamati per riposizionare l'elemento all'interno di .</span><span class="sxs-lookup"><span data-stu-id="4e4ca-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="4e4ca-108">Quando un utente fa clic su un pulsante, viene attivato il metodo correlato.</span><span class="sxs-lookup"><span data-stu-id="4e4ca-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="4e4ca-109">Nell'esempio code-behind seguente vengono <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestiti i metodi che generano gli eventi del pulsante.</span><span class="sxs-lookup"><span data-stu-id="4e4ca-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="4e4ca-110">L'esempio scrive queste <xref:System.Windows.Controls.TextBlock> chiamate al metodo negli elementi che usano metodi get correlati per restituire i nuovi valori delle proprietà come stringhe.</span><span class="sxs-lookup"><span data-stu-id="4e4ca-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="4e4ca-111">Ecco il risultato finale!</span><span class="sxs-lookup"><span data-stu-id="4e4ca-111">Here is the finished result!</span></span>

 ![una schermata illustra un'interfaccia utente WPF con due colonne, il lato destro ha una griglia 3 x 3 e la sinistra ha pulsanti per spostare un rettangolo colorato tra le colonne e le righe della griglia](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="4e4ca-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e4ca-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="4e4ca-114">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="4e4ca-114">Panels Overview</span></span>](panels-overview.md)
