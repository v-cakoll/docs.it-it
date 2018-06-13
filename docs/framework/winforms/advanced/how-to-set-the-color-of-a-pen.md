---
title: 'Procedura: impostare il colore di un oggetto Pen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: 37bc289fa1eeb7ef5510474dff062ae76be5fc65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522382"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="0acd7-102">Procedura: impostare il colore di un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="0acd7-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="0acd7-103">Questo esempio viene modificato il colore di pre-esistente <xref:System.Drawing.Pen> oggetto</span><span class="sxs-lookup"><span data-stu-id="0acd7-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="0acd7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0acd7-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0acd7-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0acd7-105">Compiling the Code</span></span>  
 <span data-ttu-id="0acd7-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0acd7-106">This example requires:</span></span>  
  
-   <span data-ttu-id="0acd7-107">Oggetto <xref:System.Drawing.Pen> oggetto denominato `myPen`.</span><span class="sxs-lookup"><span data-stu-id="0acd7-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0acd7-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="0acd7-108">Robust Programming</span></span>  
 <span data-ttu-id="0acd7-109">È necessario chiamare <xref:System.Drawing.Pen.Dispose%2A> sugli oggetti che utilizzano risorse di sistema (ad esempio <xref:System.Drawing.Pen> oggetti) al termine del loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0acd7-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acd7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0acd7-110">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="0acd7-111">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="0acd7-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="0acd7-112">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="0acd7-112">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="0acd7-113">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="0acd7-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="0acd7-114">Penne, linee e rettangoli in GDI+</span><span class="sxs-lookup"><span data-stu-id="0acd7-114">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
