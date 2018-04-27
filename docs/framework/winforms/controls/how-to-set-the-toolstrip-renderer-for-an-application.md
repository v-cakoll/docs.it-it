---
title: "Procedura: impostare il renderer ToolStrip per un'applicazione"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5bdd0d1742e02182b2a610d935bdb2a0192486fc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a>Procedura: impostare il renderer ToolStrip per un'applicazione
È possibile personalizzare l'aspetto dei singoli controlli <xref:System.Windows.Forms.ToolStrip> o di tutti i controlli <xref:System.Windows.Forms.ToolStrip> presenti nell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene dimostrato come applicare selettivamente un renderer personalizzato a un controllo <xref:System.Windows.Forms.ToolStrip> e a un controllo <xref:System.Windows.Forms.MenuStrip>.  
  
 Per usare questo esempio di codice, compilare ed eseguire l'applicazione, quindi selezionare l'ambito del rendering personalizzato dal controllo <xref:System.Windows.Forms.ComboBox>. Scegliere **Applica** per impostare il renderer.  
  
 Per visualizzare il rendering della voce di menu personalizzate, selezionare il <xref:System.Windows.Forms.MenuStrip> opzione il <xref:System.Windows.Forms.ComboBox> controllo, fare clic su **applica**e quindi aprire il **File** voce di menu.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 Impostare la proprietà <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per applicare un renderer personalizzato a tutti i controlli <xref:System.Windows.Forms.ToolStrip> dell'applicazione.  
  
 Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> per applicare un renderer personalizzato a un singolo controllo <xref:System.Windows.Forms.ToolStrip>.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 [Controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
