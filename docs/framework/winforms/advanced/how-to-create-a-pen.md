---
title: 'Procedura: Creare un oggetto Pen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: 3d88824845bf357dd9ee5f1ee8fd02f095aee605
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716920"
---
# <a name="how-to-create-a-pen"></a><span data-ttu-id="8845c-102">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="8845c-102">How to: Create a Pen</span></span>
<span data-ttu-id="8845c-103">Questo esempio viene creato un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="8845c-103">This example creates a <xref:System.Drawing.Pen> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8845c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8845c-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8845c-105">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="8845c-105">Robust Programming</span></span>  
 <span data-ttu-id="8845c-106">Dopo aver terminato di utilizzare gli oggetti che utilizzano le risorse di sistema, ad esempio <xref:System.Drawing.Pen> oggetti, è necessario chiamare <xref:System.Drawing.Pen.Dispose%2A> su di essi.</span><span class="sxs-lookup"><span data-stu-id="8845c-106">After you have finished using objects that consume system resources, such as <xref:System.Drawing.Pen> objects, you should call <xref:System.Drawing.Pen.Dispose%2A> on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8845c-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8845c-107">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="8845c-108">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="8845c-108">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="8845c-109">Penne, linee e rettangoli in GDI+</span><span class="sxs-lookup"><span data-stu-id="8845c-109">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
