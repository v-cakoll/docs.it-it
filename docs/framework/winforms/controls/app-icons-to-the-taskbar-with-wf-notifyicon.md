---
title: Aggiungere icone dell'applicazione alla barra delle applicazioni con il componente NotifyIcon
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: 46b50ecaabe75dba08fea922d7b5639031692269
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746243"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Procedura: aggiungere icone alla barra delle applicazioni mediante il componente NotifyIcon Windows Form

Il componente Windows Forms <xref:System.Windows.Forms.NotifyIcon> Visualizza una singola icona nell'area di notifica dello stato della barra delle applicazioni. Per visualizzare più icone nell'area stato, è necessario che nel form siano presenti più componenti <xref:System.Windows.Forms.NotifyIcon>. Per impostare l'icona visualizzata per un controllo, utilizzare la proprietà <xref:System.Windows.Forms.NotifyIcon.Icon%2A>. È anche possibile scrivere codice nel gestore dell'evento <xref:System.Windows.Forms.NotifyIcon.DoubleClick> in modo che ciò accada quando l'utente fa doppio clic sull'icona. È ad esempio possibile fare in modo che venga visualizzata una finestra di dialogo in cui l'utente può configurare il processo in background rappresentato dall'icona.

> [!NOTE]
> Il componente <xref:System.Windows.Forms.NotifyIcon> viene utilizzato solo a scopo di notifica, per segnalare agli utenti che si è verificata un'azione o un evento o che è stata apportata una modifica allo stato di un determinato ordinamento. È consigliabile utilizzare i menu, le barre degli strumenti e altri elementi dell'interfaccia utente per l'interazione standard con le applicazioni.

### <a name="to-set-the-icon"></a>Per impostare l'icona

1. Assegnare un valore alla proprietà <xref:System.Windows.Forms.NotifyIcon.Icon%2A>. Il valore deve essere di tipo `System.Drawing.Icon` e può essere caricato da un file con estensione ico. È possibile specificare il file icona nel codice o facendo clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nella Finestra Proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.NotifyIcon.Icon%2A> nella finestra **Proprietà** e quindi selezionando il file nella finestra di dialogo **Apri** visualizzata.

2. Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.Visible%2A> su `true`.

3. Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.Text%2A> su una stringa di descrizione comando appropriata.

     Nell'esempio di codice seguente il percorso impostato per la posizione dell'icona è la cartella **documenti** . Questo percorso viene usato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa cartella. La scelta di questa località consente anche agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo sicuro. L'esempio seguente richiede un modulo con un controllo <xref:System.Windows.Forms.NotifyIcon> già aggiunto. Richiede anche un file di icona denominato `Icon.ico`.

    ```vb
    ' You should replace the bold icon in the sample below
    ' with an icon of your own choosing.
    NotifyIcon1.Icon = New _
       System.Drawing.Icon(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Icon.ico")
    NotifyIcon1.Visible = True
    NotifyIcon1.Text = "Antivirus program"
    ```

    ```csharp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    // Note the escape character used (@) when specifying the path.
    notifyIcon1.Icon =
       new System.Drawing.Icon (System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Icon.ico");
    notifyIcon1.Visible = true;
    notifyIcon1.Text = "Antivirus program";
    ```

    ```cpp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    notifyIcon1->Icon = gcnew
       System::Drawing::Icon(String::Concat
       (System::Environment::GetFolderPath
       (System::Environment::SpecialFolder::Personal),
       "\\Icon.ico"));
    notifyIcon1->Visible = true;
    notifyIcon1->Text = "Antivirus program";
    ```

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Procedura: Associare un menu di scelta rapida a un componente NotifyIcon di Windows Form](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [Componente NotifyIcon](notifyicon-component-windows-forms.md)
- [Panoramica sul componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
