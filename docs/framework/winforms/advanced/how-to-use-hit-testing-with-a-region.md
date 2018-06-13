---
title: "Procedura: eseguire l'hit testing utilizzando una regione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 40297fada3d042aee8c317eb787de03662f86cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523086"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="85284-102">Procedura: eseguire l'hit testing utilizzando una regione</span><span class="sxs-lookup"><span data-stu-id="85284-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="85284-103">Lo scopo del processo di hit testing consiste nel determinare se il cursore è posizionato su un oggetto specificato, ad esempio un'icona o di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="85284-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85284-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="85284-104">Example</span></span>  
 <span data-ttu-id="85284-105">L'esempio seguente crea un'area a forma di segno più per l'unione di due aree rettangolari.</span><span class="sxs-lookup"><span data-stu-id="85284-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="85284-106">Si supponga che la variabile `point` contenga la posizione di clic più recente.</span><span class="sxs-lookup"><span data-stu-id="85284-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="85284-107">Il codice verifica se `point` nell'area a forma di segno più.</span><span class="sxs-lookup"><span data-stu-id="85284-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="85284-108">Se il punto nell'area (un riscontro), l'area viene riempita con colore rosso opaco.</span><span class="sxs-lookup"><span data-stu-id="85284-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="85284-109">In caso contrario, l'area viene riempita con rosso semitrasparente.</span><span class="sxs-lookup"><span data-stu-id="85284-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="85284-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="85284-110">Compiling the Code</span></span>  
 <span data-ttu-id="85284-111">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="85284-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85284-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85284-112">See Also</span></span>  
 <xref:System.Drawing.Region>  
 [<span data-ttu-id="85284-113">Regioni in GDI+</span><span class="sxs-lookup"><span data-stu-id="85284-113">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [<span data-ttu-id="85284-114">Procedura: Definire l'area di visualizzazione usando una regione</span><span class="sxs-lookup"><span data-stu-id="85284-114">How to: Use Clipping with a Region</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
