---
title: 'Procedura: gestire gli input da tastiera a livello di form'
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
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff2539ef6bb093ea026b3578250e4ec3a4cf1a19
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a>Procedura: gestire gli input da tastiera a livello di form
Windows Form consente di gestire i messaggi della tastiera a livello di form, prima che i messaggi raggiungano un controllo. Questo argomento illustra come completare questa attività.  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a>Per gestire un messaggio della tastiera a livello di form  
  
-   Gestire l'evento <xref:System.Windows.Forms.Control.KeyPress> o <xref:System.Windows.Forms.Control.KeyDown> del form di avvio e impostare la proprietà <xref:System.Windows.Forms.Form.KeyPreview%2A> del form su `true` in modo che i messaggi della tastiera vengano ricevuti dal form prima che raggiungano un controllo qualsiasi del form. L'esempio di codice seguente gestisce l'evento <xref:System.Windows.Forms.Control.KeyPress> rilevando tutti i tasti numerici e usando "1", "4" e "7".  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente è l'applicazione completa dell'esempio precedente. L'applicazione include un oggetto <xref:System.Windows.Forms.TextBox> insieme a diversi altri controlli che consentono di spostare lo stato attivo da <xref:System.Windows.Forms.TextBox>. L'evento <xref:System.Windows.Forms.Control.KeyPress> dell'oggetto <xref:System.Windows.Forms.Form> principale usa "1", "4" e "7" e l'evento <xref:System.Windows.Forms.Control.KeyPress> di <xref:System.Windows.Forms.TextBox> usa "2", "5" e "8" durante la visualizzazione dei tasti rimanenti. Confrontare l'output di <xref:System.Windows.Forms.MessageBox> quando si preme un tasto numerico mentre lo stato attivo è su <xref:System.Windows.Forms.TextBox> con l'output di <xref:System.Windows.Forms.MessageBox> quando si preme un tasto numerico mentre lo stato attivo è su uno degli altri controlli.  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 [Input da tastiera in un'applicazione Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
