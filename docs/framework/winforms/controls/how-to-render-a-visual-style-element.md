---
title: 'Procedura: eseguire il rendering di un elemento dello stile visivo'
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
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b96f9e6cc54e028e94cc7ae377012ac4f1328bb0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-render-a-visual-style-element"></a>Procedura: eseguire il rendering di un elemento dello stile visivo
Il <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> espone lo spazio dei nomi <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> elementi (UI) supportati dagli stili dell'interfaccia utente gli oggetti che rappresentano l'utente di Windows. In questo argomento viene illustrato come utilizzare il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> classe per eseguire il rendering di <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> che rappresenta il **Disconnetti** e **Arresta** pulsanti del menu Start.  
  
### <a name="to-render-a-visual-style-element"></a>Per eseguire il rendering di un elemento dello stile di visualizzazione  
  
1.  Creare un <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> e impostarla per l'elemento che si desidera creare. Si noti l'uso del <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> proprietà e <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> (metodo); il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> costruttore genera un'eccezione se gli stili di visualizzazione sono disabilitate o non è definito un elemento.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  Chiamare il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> metodo per il rendering dell'elemento che la <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> attualmente rappresenta.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo personalizzato derivato dalla <xref:System.Windows.Forms.Control> classe.  
  
-   Oggetto <xref:System.Windows.Forms.Form> che ospita il controllo personalizzato.  
  
-   I riferimenti al <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, e <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> gli spazi dei nomi.  
  
## <a name="see-also"></a>Vedere anche  
 [Rendering dei controlli con stili visivi](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
