---
title: 'Procedura: definire l''area di visualizzazione utilizzando una regione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 281ae701bc3e5cee38952a05474360019f76a665
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="91450-102">Procedura: definire l'area di visualizzazione utilizzando una regione</span><span class="sxs-lookup"><span data-stu-id="91450-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="91450-103">Una delle proprietà del <xref:System.Drawing.Graphics> classe è l'area di ritaglio.</span><span class="sxs-lookup"><span data-stu-id="91450-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="91450-104">Tutti i disegni effettuati un determinato <xref:System.Drawing.Graphics> è limitato per l'area di ritaglio di tale oggetto <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="91450-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="91450-105">È possibile impostare l'area di ritaglio chiamando il <xref:System.Drawing.Graphics.SetClip%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="91450-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91450-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="91450-106">Example</span></span>  
 <span data-ttu-id="91450-107">Nell'esempio seguente crea un percorso costituito da un singolo poligono.</span><span class="sxs-lookup"><span data-stu-id="91450-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="91450-108">Nel codice viene quindi creata un'area, in base a tale percorso.</span><span class="sxs-lookup"><span data-stu-id="91450-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="91450-109">L'area viene passata per il <xref:System.Drawing.Graphics.SetClip%2A> metodo di un <xref:System.Drawing.Graphics> oggetto e quindi due stringhe vengono disegnati.</span><span class="sxs-lookup"><span data-stu-id="91450-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="91450-110">Nella figura seguente mostra le stringhe tagliate.</span><span class="sxs-lookup"><span data-stu-id="91450-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="91450-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="91450-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="91450-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="91450-112">Compiling the Code</span></span>  
 <span data-ttu-id="91450-113">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="91450-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91450-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91450-114">See Also</span></span>  
 [<span data-ttu-id="91450-115">Regioni in GDI+</span><span class="sxs-lookup"><span data-stu-id="91450-115">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [<span data-ttu-id="91450-116">Uso delle regioni</span><span class="sxs-lookup"><span data-stu-id="91450-116">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
