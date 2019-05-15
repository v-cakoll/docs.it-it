---
title: 'Procedura: Creare un modulo con interfaccia a documenti multipli con unione di menu e controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 0edcc27968c55908cda0e881ed66f83323316711
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591312"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Procedura: Creare un modulo con interfaccia a documenti multipli con unione di menu e controlli ToolStrip
Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu. I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.  
  
 È disponibile supporto completo per questa funzionalità in Visual Studio.  
  
 Vedere anche [procedura dettagliata: Creazione di un Form MDI con unione di Menu e controlli ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come usare i controlli <xref:System.Windows.Forms.ToolStripPanel> con un form MDI. Il form supporta anche l'unione dei menu con menu figlio.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo ToolStrip](toolstrip-control-windows-forms.md)
