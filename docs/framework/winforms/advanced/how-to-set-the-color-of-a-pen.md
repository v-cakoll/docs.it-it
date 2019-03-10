---
title: 'Procedura: Impostare il colore di un oggetto Pen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: a2645112950be88cbc569e0be7889c0f1019223d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710385"
---
# <a name="how-to-set-the-color-of-a-pen"></a>Procedura: Impostare il colore di un oggetto Pen
Questo esempio viene modificato il colore di un preesistenti <xref:System.Drawing.Pen> oggetto  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Oggetto <xref:System.Drawing.Pen> oggetto denominato `myPen`.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 È necessario chiamare <xref:System.Drawing.Pen.Dispose%2A> sugli oggetti che utilizzano le risorse di sistema (ad esempio <xref:System.Drawing.Pen> oggetti) al termine del loro utilizzo.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Pen>
- [Introduzione alla programmazione grafica](getting-started-with-graphics-programming.md)
- [Procedura: Creare un oggetto Pen](how-to-create-a-pen.md)
- [Uso di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
- [Penne, linee e rettangoli in GDI+](pens-lines-and-rectangles-in-gdi.md)
