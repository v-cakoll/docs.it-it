---
title: "Procedura: Gestire l'input da tastiera a livello di modulo"
description: Informazioni su come gestire l'input da tastiera per il Windows Forms a livello di form, prima che i messaggi raggiungano un controllo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: 6f0695b6f665a613e0e4e001a4f9bbfc09dd45ed
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904156"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a>Procedura: Gestire l'input da tastiera a livello di modulo
Windows Form consente di gestire i messaggi della tastiera a livello di form, prima che i messaggi raggiungano un controllo. Questo argomento illustra come completare questa attività.  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a>Per gestire un messaggio della tastiera a livello di form  
  
- Gestire l'evento <xref:System.Windows.Forms.Control.KeyPress> o <xref:System.Windows.Forms.Control.KeyDown> del form di avvio e impostare la proprietà <xref:System.Windows.Forms.Form.KeyPreview%2A> del form su `true` in modo che i messaggi della tastiera vengano ricevuti dal form prima che raggiungano un controllo qualsiasi del form. L'esempio di codice seguente gestisce l'evento <xref:System.Windows.Forms.Control.KeyPress> rilevando tutti i tasti numerici e usando "1", "4" e "7".  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente è l'applicazione completa dell'esempio precedente. L'applicazione include un oggetto <xref:System.Windows.Forms.TextBox> insieme a diversi altri controlli che consentono di spostare lo stato attivo da <xref:System.Windows.Forms.TextBox>. L'evento <xref:System.Windows.Forms.Control.KeyPress> dell'oggetto <xref:System.Windows.Forms.Form> principale usa "1", "4" e "7" e l'evento <xref:System.Windows.Forms.Control.KeyPress> di <xref:System.Windows.Forms.TextBox> usa "2", "5" e "8" durante la visualizzazione dei tasti rimanenti. Confrontare l'output di <xref:System.Windows.Forms.MessageBox> quando si preme un tasto numerico mentre lo stato attivo è su <xref:System.Windows.Forms.TextBox> con l'output di <xref:System.Windows.Forms.MessageBox> quando si preme un tasto numerico mentre lo stato attivo è su uno degli altri controlli.  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- [Input da tastiera in un'applicazione Windows Form](keyboard-input-in-a-windows-forms-application.md)
