---
title: Utilizzo della trasformazione di tipo World
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: cc6bcca42e84580199f75c64087af6d98f476d4b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715698"
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="1c2c3-102">Utilizzo della trasformazione di tipo World</span><span class="sxs-lookup"><span data-stu-id="1c2c3-102">Using the World Transformation</span></span>
<span data-ttu-id="1c2c3-103">La trasformazione globale è una proprietà del <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="1c2c3-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="1c2c3-104">I numeri che specificano la trasformazione globale vengono archiviati un <xref:System.Drawing.Drawing2D.Matrix> oggetto che rappresenta una matrice 3x3.</span><span class="sxs-lookup"><span data-stu-id="1c2c3-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="1c2c3-105">Il <xref:System.Drawing.Drawing2D.Matrix> e <xref:System.Drawing.Graphics> classi dispongono di diversi metodi per impostare i numeri in matrice di trasformazione globale.</span><span class="sxs-lookup"><span data-stu-id="1c2c3-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="1c2c3-106">Diversi tipi di trasformazioni</span><span class="sxs-lookup"><span data-stu-id="1c2c3-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="1c2c3-107">Nell'esempio seguente, prima di tutto il codice crea un rettangolo di 50 x 50 e collocato in corrispondenza dell'origine (0, 0).</span><span class="sxs-lookup"><span data-stu-id="1c2c3-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="1c2c3-108">L'origine è nell'angolo superiore sinistro dell'area client.</span><span class="sxs-lookup"><span data-stu-id="1c2c3-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="1c2c3-109">Il codice seguente si applica una trasformazione di ridimensionamento che si espande il rettangolo di un fattore di 1,75 nella direzione x e riduce il rettangolo di un fattore pari a 0,5 nella direzione y:</span><span class="sxs-lookup"><span data-stu-id="1c2c3-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="1c2c3-110">Il risultato è un rettangolo che è più breve nella direzione y rispetto all'originale e più lungo nella direzione x.</span><span class="sxs-lookup"><span data-stu-id="1c2c3-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="1c2c3-111">Per ruotare il rettangolo anziché ridurlo, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1c2c3-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="1c2c3-112">Per convertire il rettangolo, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1c2c3-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="1c2c3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c2c3-113">See also</span></span>
- <xref:System.Drawing.Drawing2D.Matrix>
- [<span data-ttu-id="1c2c3-114">Sistemi di coordinate e trasformazioni</span><span class="sxs-lookup"><span data-stu-id="1c2c3-114">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="1c2c3-115">Uso di trasformazioni nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="1c2c3-115">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
