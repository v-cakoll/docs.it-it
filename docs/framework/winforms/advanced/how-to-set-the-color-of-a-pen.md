---
title: 'Procedura: impostare il colore di un oggetto Pen'
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
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66527be5a70f9c7c60f4ca3836ee68b96872442f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-color-of-a-pen"></a>Procedura: impostare il colore di un oggetto Pen
Questo esempio viene modificato il colore di pre-esistente <xref:System.Drawing.Pen> oggetto  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Oggetto <xref:System.Drawing.Pen> oggetto denominato `myPen`.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 È necessario chiamare <xref:System.Drawing.Pen.Dispose%2A> sugli oggetti che utilizzano risorse di sistema (ad esempio <xref:System.Drawing.Pen> oggetti) al termine del loro utilizzo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Pen>  
 [Introduzione alla programmazione grafica](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Procedura: Creare un oggetto Pen](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Penne, linee e rettangoli in GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
