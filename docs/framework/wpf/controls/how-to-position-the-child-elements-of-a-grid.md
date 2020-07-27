---
title: 'Procedura: posizionare gli elementi figlio di una griglia'
description: Informazioni su come usare i metodi get e set definiti in una griglia Windows Presentation Foundation per posizionare gli elementi figlio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 926d223097dd21dd0292c9523903b4be8aba8ba9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167396"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="6db52-103">Procedura: posizionare gli elementi figlio di una griglia</span><span class="sxs-lookup"><span data-stu-id="6db52-103">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="6db52-104">Questo esempio illustra come usare i metodi get e set definiti in <xref:System.Windows.Controls.Grid> per posizionare gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="6db52-104">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6db52-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6db52-105">Example</span></span>  
 <span data-ttu-id="6db52-106">Nell'esempio seguente viene definito un <xref:System.Windows.Controls.Grid> elemento padre ( `grid1` ) con tre colonne e tre righe.</span><span class="sxs-lookup"><span data-stu-id="6db52-106">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="6db52-107">Un <xref:System.Windows.Shapes.Rectangle> elemento figlio ( `rect1` ) viene aggiunto all'oggetto <xref:System.Windows.Controls.Grid> nella posizione della colonna zero, posizione riga zero.</span><span class="sxs-lookup"><span data-stu-id="6db52-107">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="6db52-108"><xref:System.Windows.Controls.Button>gli elementi rappresentano metodi che possono essere chiamati per riposizionare l' <xref:System.Windows.Shapes.Rectangle> elemento all'interno di <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="6db52-108"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="6db52-109">Quando un utente fa clic su un pulsante, il metodo correlato viene attivato.</span><span class="sxs-lookup"><span data-stu-id="6db52-109">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="6db52-110">Il seguente esempio di code-behind gestisce i metodi generati dagli <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi del pulsante.</span><span class="sxs-lookup"><span data-stu-id="6db52-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="6db52-111">L'esempio scrive queste chiamate al metodo in <xref:System.Windows.Controls.TextBlock> elementi che usano metodi Get correlati per restituire i nuovi valori di proprietà come stringhe.</span><span class="sxs-lookup"><span data-stu-id="6db52-111">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="6db52-112">Ecco il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="6db52-112">Here is the finished result!</span></span>

 ![una schermata illustra un'interfaccia utente WPF con due colonne, il lato destro ha una griglia 3 x 3 e i pulsanti a sinistra per spostare un rettangolo colorato tra le colonne e le righe della griglia](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="6db52-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6db52-114">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="6db52-115">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="6db52-115">Panels Overview</span></span>](panels-overview.md)
