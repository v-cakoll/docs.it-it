---
title: 'Procedura: Posizionare gli elementi figlio di un elemento Grid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: c508f45c1ea3d0925503d6fe5600498a0558d5ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770802"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="e5ede-102">Procedura: Posizionare gli elementi figlio di un elemento Grid</span><span class="sxs-lookup"><span data-stu-id="e5ede-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="e5ede-103">In questo esempio viene illustrato come utilizzare il metodo get e i metodi definiti nel set <xref:System.Windows.Controls.Grid> per posizionare elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="e5ede-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5ede-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5ede-104">Example</span></span>  
 <span data-ttu-id="e5ede-105">L'esempio seguente definisce un elemento padre <xref:System.Windows.Controls.Grid> elemento (`grid1`) che include tre colonne e tre righe.</span><span class="sxs-lookup"><span data-stu-id="e5ede-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="e5ede-106">Un elemento figlio <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) viene aggiunto al <xref:System.Windows.Controls.Grid> nella posizione della colonna da zero, posizione zero della riga.</span><span class="sxs-lookup"><span data-stu-id="e5ede-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="e5ede-107"><xref:System.Windows.Controls.Button> elementi rappresentano i metodi che possono essere chiamati per riposizionare le <xref:System.Windows.Shapes.Rectangle> elemento all'interno di <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="e5ede-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="e5ede-108">Quando un utente sceglie un pulsante, viene attivato il metodo correlato.</span><span class="sxs-lookup"><span data-stu-id="e5ede-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="e5ede-109">L'esempio di codice seguente gestisce i metodi che il pulsante <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dagli eventi.</span><span class="sxs-lookup"><span data-stu-id="e5ede-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="e5ede-110">L'esempio scrive queste chiamate ai metodi <xref:System.Windows.Controls.TextBlock> gli elementi correlati Usa metodi get per restituire i nuovi valori di proprietà come stringhe.</span><span class="sxs-lookup"><span data-stu-id="e5ede-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="e5ede-111">Ecco il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="e5ede-111">Here is the finished result!</span></span>
 
 ![uno screenshot viene illustrata un'interfaccia utente WPF con due colonne, la parte destra è presente una 3x3 griglia e sinistra è disponibili pulsanti per spostare un rettangolo colorato tra le colonne e righe della griglia](././media/grid-methods-sample.png) 
  
## <a name="see-also"></a><span data-ttu-id="e5ede-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5ede-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="e5ede-114">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="e5ede-114">Panels Overview</span></span>](panels-overview.md)
