---
title: 'Procedura: Usare il ritaglio per definire una regione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: e62be137b36a2f369c02151466154f6b3bab090b
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063844"
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="4a7ee-102">Procedura: Usare il ritaglio per definire una regione</span><span class="sxs-lookup"><span data-stu-id="4a7ee-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="4a7ee-103">Una delle proprietà del <xref:System.Drawing.Graphics> classe è l'area di ritaglio.</span><span class="sxs-lookup"><span data-stu-id="4a7ee-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="4a7ee-104">Tutti i disegni effettuati un determinato <xref:System.Drawing.Graphics> è limitato per l'area di ritaglio di tale oggetto <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4a7ee-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="4a7ee-105">È possibile impostare l'area di ritaglio chiamando il <xref:System.Drawing.Graphics.SetClip%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="4a7ee-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a7ee-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a7ee-106">Example</span></span>  
 <span data-ttu-id="4a7ee-107">Nell'esempio seguente crea un percorso che è costituito da un singolo poligono.</span><span class="sxs-lookup"><span data-stu-id="4a7ee-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="4a7ee-108">Nel codice viene quindi creata un'area, in base a tale percorso.</span><span class="sxs-lookup"><span data-stu-id="4a7ee-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="4a7ee-109">L'area viene passato per il <xref:System.Drawing.Graphics.SetClip%2A> metodo di un <xref:System.Drawing.Graphics> vengono disegnati oggetti e quindi due stringhe.</span><span class="sxs-lookup"><span data-stu-id="4a7ee-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="4a7ee-110">La figura seguente mostra le stringhe abbreviate:</span><span class="sxs-lookup"><span data-stu-id="4a7ee-110">The following illustration shows the clipped strings:</span></span>  
  
 ![Screenshot che mostra stringhe incomplete.](./media/how-to-use-clipping-with-a-region/clipped-strings-polygon.png)  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4a7ee-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4a7ee-112">Compiling the Code</span></span>  
 <span data-ttu-id="4a7ee-113">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="4a7ee-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a7ee-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a7ee-114">See also</span></span>

- [<span data-ttu-id="4a7ee-115">Regioni in GDI+</span><span class="sxs-lookup"><span data-stu-id="4a7ee-115">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="4a7ee-116">Uso delle regioni</span><span class="sxs-lookup"><span data-stu-id="4a7ee-116">Using Regions</span></span>](using-regions.md)
