---
title: 'Procedura: Creare un Form Windows shaping'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
ms.openlocfilehash: 937b785078e58026a5360155805f9cf37031cec6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527276"
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="f6bd1-102">Procedura: Creare un Form Windows shaping</span><span class="sxs-lookup"><span data-stu-id="f6bd1-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="f6bd1-103">In questo esempio viene creato un form una forma ellittica che viene ridimensionato con il modulo.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6bd1-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f6bd1-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f6bd1-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f6bd1-105">Compiling the Code</span></span>  
 <span data-ttu-id="f6bd1-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6bd1-106">This example requires:</span></span>  
  
-   <span data-ttu-id="f6bd1-107">Riferimenti agli spazi dei nomi <xref:System.Windows.Forms> e <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="f6bd1-108">Questo esempio sostituisce la <xref:System.Windows.Forms.Control.OnPaint%2A> metodo per modificare la forma del form.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="f6bd1-109">Per usare questo codice, copiare la dichiarazione del metodo, nonché il codice di disegno all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6bd1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6bd1-110">See also</span></span>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Region>
- <xref:System.Drawing>
- <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>
- <xref:System.Windows.Forms.Control.Region%2A>
- [<span data-ttu-id="f6bd1-111">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="f6bd1-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
