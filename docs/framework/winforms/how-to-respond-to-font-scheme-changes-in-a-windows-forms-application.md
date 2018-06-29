---
title: "Procedura: Rispondere a modifiche delle combinazioni dei tipi di carattere in un'applicazione Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 2451885c673515eb6690b0784fd5bd22de629209
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2018
ms.locfileid: "37071146"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Procedura: Rispondere a modifiche delle combinazioni dei tipi di carattere in un'applicazione Windows Form
Nei sistemi operativi Windows, un utente può modificare le impostazioni a livello di sistema per rendere il tipo di carattere predefinito più piccole o grandi dimensioni. Modifica di queste impostazioni del tipo di carattere è fondamentale per gli utenti che sono vedenti e richiedono un tipo più grande contenere il testo sullo schermo. È possibile modificare l'applicazione Windows Form da reagire a queste modifiche aumentando o riducendo le dimensioni del form e tutto il testo ogni volta che viene modificato lo schema del tipo di carattere. Se si desidera un modulo per supportare le modifiche nelle dimensioni del carattere in modo dinamico, è possibile aggiungere codice al form.  
  
 In genere, il tipo di carattere predefinito utilizzato da Windows Form viene usato il carattere restituito dal <xref:Microsoft.Win32> chiamata dello spazio dei nomi a `GetStockObject(DEFAULT_GUI_FONT)`. Il tipo di carattere restituito da questa chiamata cambia solo quando cambia la risoluzione dello schermo. Come illustrato nella procedura seguente, il codice necessario modificare il tipo di carattere predefinito <xref:System.Drawing.SystemFonts.IconTitleFont%2A> per rispondere alle modifiche apportate alle dimensioni del carattere.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Per utilizzare il tipo di carattere desktop e rispondere alle modifiche delle combinazioni di carattere  
  
1.  Creare il form e aggiungere i controlli desiderati. Per altre informazioni, vedere [procedura: creare un'applicazione Windows Forms dalla riga di comando](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) e [controlli da usare in Windows Form](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
2.  Aggiungere un riferimento al <xref:Microsoft.Win32> dello spazio dei nomi al codice.  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  Aggiungere il codice seguente al costruttore del form per associare i gestori di eventi necessarie e per modificare il tipo di carattere predefinito in uso per il form.  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  Implementare un gestore per il <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> evento che attiva il form per ridimensionare automaticamente quando il <xref:Microsoft.Win32.UserPreferenceCategory.Window> le modifiche della categoria.  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  Infine, implementare un gestore per il <xref:System.Windows.Forms.Form.FormClosing> evento che consente di scollegare il <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> gestore dell'evento.  
  
     > [!IMPORTANT]
     > L'errore per includere questo codice imposterà l'applicazione per determinare una perdita di memoria.  
  
     [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6.  Compilare ed eseguire il codice.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>Per modificare manualmente la combinazione di tipi di carattere in Windows XP  
  
1.  Durante l'esecuzione di un'applicazione Windows Form destro del mouse sul desktop di Windows e scegliere **proprietà** dal menu di scelta rapida.  
  
2.  Nel **delle proprietà di visualizzazione** finestra di dialogo, fare clic sul **aspetto** scheda.  
  
3.  Dal **Font Size** elenco a discesa, selezionare una nuova dimensione del carattere.  
  
     Si noterà che il modulo reagisce ora per le modifiche in fase di esecuzione nello schema di carattere del desktop. Quando l'utente modifica tra **normale**, **caratteri grandi**, e **caratteri molto grandi**, il modulo cambia tipo di carattere e la scala correttamente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Il costruttore in questo esempio di codice contiene una chiamata a `InitializeComponent`, che viene definito quando si crea un nuovo progetto Windows Form in Visual Studio. Rimuovere questa riga di codice se si compila l'applicazione nella riga di comando.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [Ridimensionamento automatico in Windows Form](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
