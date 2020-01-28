---
title: Rispondere alle modifiche dello schema dei tipi di carattere in un'app Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739231"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Procedura: Rispondere a modifiche delle combinazioni dei tipi di carattere in un'applicazione Windows Form
Nei sistemi operativi Windows, un utente può modificare le impostazioni del tipo di carattere a livello di sistema in modo che il tipo di carattere predefinito risulti più grande o più piccolo. La modifica di queste impostazioni dei tipi di carattere è fondamentale per gli utenti che hanno un impatto visivo e richiedono un tipo più grande per leggere il testo sulle schermate. È possibile modificare le Windows Forms Application per rispondere a queste modifiche aumentando o diminuendo le dimensioni del form e tutto il testo contenuto ogni volta che lo schema del tipo di carattere viene modificato. Se si desidera che il form soddisfi le modifiche delle dimensioni dei tipi di carattere in modo dinamico, è possibile aggiungere codice al form.  
  
 In genere, il tipo di carattere predefinito usato da Windows Forms è il tipo di carattere restituito dalla chiamata dello spazio dei nomi <xref:Microsoft.Win32> a `GetStockObject(DEFAULT_GUI_FONT)`. Il tipo di carattere restituito da questa chiamata viene modificato solo quando cambia la risoluzione dello schermo. Come illustrato nella procedura seguente, il codice deve modificare il tipo di carattere predefinito in <xref:System.Drawing.SystemFonts.IconTitleFont%2A> per rispondere alle modifiche apportate alle dimensioni del carattere.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Per utilizzare il tipo di carattere desktop e rispondere alle modifiche dello schema del carattere  
  
1. Creare il form e aggiungere i controlli desiderati. Per altre informazioni, vedere [procedura: creare un'applicazione Windows Forms dalla riga di comando](how-to-create-a-windows-forms-application-from-the-command-line.md) e [controlli da usare in Windows Forms](./controls/controls-to-use-on-windows-forms.md).  
  
2. Aggiungere un riferimento allo spazio dei nomi <xref:Microsoft.Win32> al codice.  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. Aggiungere il codice seguente al costruttore del form per associare i gestori eventi obbligatori e per modificare il tipo di carattere predefinito in uso per il form.  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. Implementare un gestore per l'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> che determina la scalabilità automatica del modulo quando cambia la categoria <xref:Microsoft.Win32.UserPreferenceCategory.Window>.  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. Infine, implementare un gestore per l'evento <xref:System.Windows.Forms.Form.FormClosing> che scollega il gestore dell'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.  
  
     > [!IMPORTANT]
     > La mancata inclusione di questo codice causerà la perdita di memoria da un'applicazione.  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. Compilare ed eseguire il codice.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>Per modificare manualmente lo schema dei tipi di carattere in Windows XP  
  
1. Mentre il Windows Forms Application è in esecuzione, fare clic con il pulsante destro del mouse sul desktop di Windows e scegliere **Proprietà** dal menu di scelta rapida.  
  
2. Nella finestra di dialogo **proprietà di visualizzazione** fare clic sulla scheda **aspetto** .  
  
3. Nella casella di riepilogo a discesa **dimensioni carattere** selezionare una nuova dimensione del carattere.  
  
     Si noterà che il modulo ora reagisce alle modifiche della fase di esecuzione nello schema del tipo di carattere del desktop. Quando l'utente passa da un tipo di carattere **normale**a un carattere di **grandi dimensioni**e da **caratteri molto grandi**, il form modifica il tipo di carattere e ridimensiona correttamente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Il costruttore in questo esempio di codice contiene una chiamata a `InitializeComponent`, che viene definita quando si crea un nuovo progetto di Windows Forms in Visual Studio. Rimuovere questa riga di codice se si compila l'applicazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [Ridimensionamento automatico in Windows Form](automatic-scaling-in-windows-forms.md)
