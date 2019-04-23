---
title: 'Procedura: Creare un oggetto Solid Brush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: ed9ec1f52b41c83b3cc6e36dedf97f1c00db42e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213441"
---
# <a name="how-to-create-a-solid-brush"></a><span data-ttu-id="ac31c-102">Procedura: Creare un oggetto Solid Brush</span><span class="sxs-lookup"><span data-stu-id="ac31c-102">How to: Create a Solid Brush</span></span>
<span data-ttu-id="ac31c-103">Questo esempio viene creato un <xref:System.Drawing.SolidBrush> oggetto che può essere usato da un <xref:System.Drawing.Graphics> oggetto per il riempimento di forme.</span><span class="sxs-lookup"><span data-stu-id="ac31c-103">This example creates a <xref:System.Drawing.SolidBrush> object that can be used by a <xref:System.Drawing.Graphics> object for filling shapes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac31c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac31c-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ac31c-105">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="ac31c-105">Robust Programming</span></span>  
 <span data-ttu-id="ac31c-106">Dopo aver usarle, è necessario chiamare <xref:System.IDisposable.Dispose%2A> su oggetti che utilizzano le risorse di sistema, ad esempio gli oggetti pennello.</span><span class="sxs-lookup"><span data-stu-id="ac31c-106">After you have finished using them, you should call <xref:System.IDisposable.Dispose%2A> on objects that consume system resources, such as brush objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac31c-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac31c-107">See also</span></span>

- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="ac31c-108">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="ac31c-108">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="ac31c-109">Pennelli e forme con riempimento in GDI+</span><span class="sxs-lookup"><span data-stu-id="ac31c-109">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
- [<span data-ttu-id="ac31c-110">Uso di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="ac31c-110">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
