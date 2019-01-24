---
title: "Procedura: Eseguire l'Hit Testing utilizzando una regione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 1866810b875063271e206da1fe5d6fc06f7b5de0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564305"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="3a34b-102">Procedura: Eseguire l'Hit Testing utilizzando una regione</span><span class="sxs-lookup"><span data-stu-id="3a34b-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="3a34b-103">Lo scopo dell'hit testing è determinare se il cursore si trova su un determinato oggetto, ad esempio un'icona o un pulsante.</span><span class="sxs-lookup"><span data-stu-id="3a34b-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a34b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a34b-104">Example</span></span>  
 <span data-ttu-id="3a34b-105">L'esempio seguente crea un'area a forma di segno più per formare l'unione di due aree rettangolari.</span><span class="sxs-lookup"><span data-stu-id="3a34b-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="3a34b-106">Si supponga che la variabile `point` contiene la posizione di clic con il più recente.</span><span class="sxs-lookup"><span data-stu-id="3a34b-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="3a34b-107">Il codice verifica se `point` nell'area a forma di segno più.</span><span class="sxs-lookup"><span data-stu-id="3a34b-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="3a34b-108">Se il punto nell'area (hit), l'area viene riempita con un pennello opaco rosso.</span><span class="sxs-lookup"><span data-stu-id="3a34b-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="3a34b-109">In caso contrario, l'area viene riempita con un pennello di colore rosso semitrasparente.</span><span class="sxs-lookup"><span data-stu-id="3a34b-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a34b-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3a34b-110">Compiling the Code</span></span>  
 <span data-ttu-id="3a34b-111">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="3a34b-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a34b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a34b-112">See also</span></span>
- <xref:System.Drawing.Region>
- [<span data-ttu-id="3a34b-113">Regioni in GDI+</span><span class="sxs-lookup"><span data-stu-id="3a34b-113">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)
- [<span data-ttu-id="3a34b-114">Procedura: Uso con un'area di ritaglio</span><span class="sxs-lookup"><span data-stu-id="3a34b-114">How to: Use Clipping with a Region</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
