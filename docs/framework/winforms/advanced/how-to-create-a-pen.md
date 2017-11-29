---
title: 'Procedura: creare un oggetto Pen'
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
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 402881d31c14b4223144792e081324fb113162a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-pen"></a><span data-ttu-id="e60b3-102">Procedura: creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="e60b3-102">How to: Create a Pen</span></span>
<span data-ttu-id="e60b3-103">Questo esempio viene creato un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e60b3-103">This example creates a <xref:System.Drawing.Pen> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e60b3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e60b3-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e60b3-105">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e60b3-105">Robust Programming</span></span>  
 <span data-ttu-id="e60b3-106">Dopo aver terminato di utilizzare gli oggetti che utilizzano risorse di sistema, ad esempio <xref:System.Drawing.Pen> oggetti, è necessario chiamare <xref:System.Drawing.Pen.Dispose%2A> su di essi.</span><span class="sxs-lookup"><span data-stu-id="e60b3-106">After you have finished using objects that consume system resources, such as <xref:System.Drawing.Pen> objects, you should call <xref:System.Drawing.Pen.Dispose%2A> on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e60b3-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e60b3-107">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="e60b3-108">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="e60b3-108">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="e60b3-109">Penne, linee e rettangoli in GDI+</span><span class="sxs-lookup"><span data-stu-id="e60b3-109">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
