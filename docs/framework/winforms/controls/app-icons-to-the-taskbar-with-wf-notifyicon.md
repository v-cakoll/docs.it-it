---
title: 'Procedura: aggiungere icone alla barra delle applicazioni mediante il componente NotifyIcon Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d795df8e8b514345632491fd6afdd618c2f18ec2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Procedura: aggiungere icone alla barra delle applicazioni mediante il componente NotifyIcon Windows Form
Windows Form <xref:System.Windows.Forms.NotifyIcon> componente consente di visualizzare una singola icona nell'area di notifica dello stato della barra delle applicazioni. Per visualizzare le icone più nell'area di stato, è necessario disporre di più <xref:System.Windows.Forms.NotifyIcon> componenti nel form. Per impostare l'icona visualizzata per un controllo, utilizzare il <xref:System.Windows.Forms.NotifyIcon.Icon%2A> proprietà. È anche possibile scrivere codice nel <xref:System.Windows.Forms.NotifyIcon.DoubleClick> gestore dell'evento in modo che si verifica un evento quando l'utente fa doppio clic sull'icona. Ad esempio, è possibile apportare a una finestra di dialogo vengono visualizzati all'utente di configurare il processo in background rappresentato dall'icona.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.NotifyIcon> componente viene utilizzato solo a fini di notifica per avvisare gli utenti che si è verificato un evento o azione o si è verificato un cambiamento dello stato di qualche tipo. Utilizzare i menu, barre degli strumenti e altri elementi dell'interfaccia utente per l'interazione standard con le applicazioni.  
  
### <a name="to-set-the-icon"></a>Per impostare l'icona  
  
1.  Assegnare un valore per il <xref:System.Windows.Forms.NotifyIcon.Icon%2A> proprietà. Il valore deve essere di tipo `System.Drawing.Icon` e può essere caricato da un file con estensione ico. È possibile specificare il file dell'icona nel codice o fare clic sul pulsante dei puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.NotifyIcon.Icon%2A> proprietà il  **Proprietà** finestra e quindi selezionare il file nel **aprire** la finestra di dialogo visualizzata.  
  
2.  Impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.Visible%2A> su `true`.  
  
3.  Impostare il <xref:System.Windows.Forms.NotifyIcon.Text%2A> proprietà da una stringa di descrizione appropriata.  
  
     Nell'esempio di codice riportato di seguito, il percorso impostato per la posizione dell'icona è il **documenti** cartella. Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella. Questa scelta consente inoltre agli utenti con livelli di accesso di sistema minimi eseguire in modo sicuro l'applicazione. L'esempio seguente richiede un form con un <xref:System.Windows.Forms.NotifyIcon> controllo già aggiunto. È inoltre necessario un file di icona denominato `Icon.ico`.  
  
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
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [Procedura: Associare un menu di scelta rapida a un componente NotifyIcon di Windows Form](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [Componente NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [Panoramica sul componente NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
