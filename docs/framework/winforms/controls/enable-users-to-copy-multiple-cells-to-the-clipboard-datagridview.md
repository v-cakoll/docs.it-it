---
title: "Procedura: consentire agli utenti di copiare più celle negli Appunti dal controllo DataGridView di Windows Form"
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
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 703284572005ab262a7e9379b601d8144d8e9af1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a>Procedura: consentire agli utenti di copiare più celle negli Appunti dal controllo DataGridView di Windows Form
Quando si attiva la copia delle celle, i dati contenuti nel controllo <xref:System.Windows.Forms.DataGridView> sono facilmente accessibili da altre applicazioni tramite la classe <xref:System.Windows.Forms.Clipboard>. I valori delle celle selezionate vengono convertiti in stringhe e aggiunti negli Appunti sotto forma di valori di testo delimitato da tabulazioni, per consentirne l'inserimento in applicazioni quali Blocco note ed Excel, e sotto forma di una tabella in formato HTML, per consentirne l'inserimento in applicazioni come Word.  
  
 È possibile configurare la funzionalità di copia dalle celle in modo da copiare solo i valori delle celle, includere il testo della riga e dell'intestazione della colonna nei dati degli Appunti o includere il testo dell'intestazione solo quando gli utenti selezionano righe o colonne intere.  
  
 A seconda della modalità di selezione gli utenti possono selezionare più gruppi di celle scollegati. Quando un utente copia le celle negli Appunti, le righe e le colonne in cui non è selezionata alcuna cella non vengono copiate. Tutte le altre righe o colonne diventano righe o colonne nella tabella di dati copiati negli Appunti.  Le celle non selezionate in queste righe o colonne vengono copiate come segnaposto vuoti negli Appunti.  
  
### <a name="to-enable-cell-copying"></a>Per abilitare la copia delle celle  
  
-   Impostare la proprietà <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice completo seguente viene illustrato come le celle vengono copiate negli Appunti. In questo esempio è incluso un pulsante che consente di copiare le celle selezionate negli Appunti mediante il metodo <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> e viene visualizzato il contenuto degli Appunti in una casella di testo.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per questo codice sono necessari i requisiti seguenti:  
  
-   Riferimenti agli assembly N:System e N:System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>  
 [Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
