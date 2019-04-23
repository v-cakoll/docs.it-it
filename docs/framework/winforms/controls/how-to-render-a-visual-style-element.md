---
title: 'Procedura: Eseguire il rendering di un elemento dello stile visivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: 57c2bc5722f77338225d70b514345344211656dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312397"
---
# <a name="how-to-render-a-visual-style-element"></a>Procedura: Eseguire il rendering di un elemento dello stile visivo
Il <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> dello spazio dei nomi espone <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> elementi (UI) supportati dagli stili dell'interfaccia utente gli oggetti che rappresentano l'utente di Windows. In questo argomento illustra come usare il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> classe per eseguire il rendering le <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> che rappresenta il **Disconnetti** e **Spegni** pulsanti del menu Start.  
  
### <a name="to-render-a-visual-style-element"></a>Per eseguire il rendering di un elemento dello stile di visualizzazione  
  
1. Creare un <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> e impostarlo per l'elemento che si desidera disegnare. Si noti l'uso del <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> proprietà e il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> metodo; il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> costruttore verrà generata un'eccezione se sono disabilitati o non è definito un elemento.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2. Chiamare il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> metodo per il rendering dell'elemento che il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> rappresenta attualmente.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo personalizzato derivato dal <xref:System.Windows.Forms.Control> classe.  
  
-   Oggetto <xref:System.Windows.Forms.Form> che ospita il controllo personalizzato.  
  
-   Fa riferimento per la <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, e <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> gli spazi dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- [Rendering dei controlli con stili visivi](rendering-controls-with-visual-styles.md)
