---
title: 'Procedura: convalidare le impostazioni applicazione'
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
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 309429c2481bad3a8dff4708d9e2ea8a03057a4e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-application-settings"></a>Procedura: convalidare le impostazioni applicazione
In questo argomento viene illustrato come convalidare le impostazioni dell'applicazione prima dell'operazione che le rende persistenti.  
  
 Poiché le impostazioni dell'applicazione sono fortemente tipizzate, è necessario in qualche modo che gli utenti non possano assegnare dati di tipo non corretto a una determinata impostazione. Un utente potrebbe comunque provare ad assegnare un valore a un'impostazione che non rientra nei limiti accettabili, ad esempio, fornendo una data di nascita che ha luogo nel futuro. <xref:System.Configuration.ApplicationSettingsBase>, la classe padre di tutte le classi di impostazioni applicazione, espone quattro eventi da abilitare tali controllo dei limiti. La gestione di tali eventi inserisce tutto il codice di convalida in un'unica posizione, invece di distribuirlo in tutto il progetto.  
  
 L'evento da usare dipende da quando è necessario convalidare le impostazioni, come descritto nella tabella seguente.  
  
|Evento|Occorrenza e uso|  
|-----------|------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|Si verifica dopo il caricamento iniziale di un gruppo di proprietà delle impostazioni.<br /><br /> Usare questo evento per convalidare i valori iniziali per l'intero gruppo di proprietà prima che vengano usati all'interno dell'applicazione.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|Si verifica prima che venga modificato il valore di una singola proprietà delle impostazioni.<br /><br /> Usare questo evento per convalidare una singola proprietà prima che venga modificata. Può offrire un feedback immediato agli utenti in relazione alle loro azioni e scelte.|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|Si verifica quando viene modificato il valore di una singola proprietà delle impostazioni.<br /><br /> Usare questo evento per convalidare una singola proprietà dopo che è stata modificata. Questo evento viene raramente usato per la convalida a meno che non sia necessario un lungo e asincrono processo di convalida.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|Si verifica prima che il gruppo di impostazioni della proprietà venga archiviato.<br /><br /> Usare questo evento per convalidare i valori per l'intero gruppo di proprietà prima che siano resi persistenti sul disco.|  
  
 In genere, non si usano tutti questi eventi all'interno della stessa applicazione ai fini della convalida. Ad esempio, è possibile soddisfare tutti i requisiti di convalida gestendo solo il <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> evento.  
  
 Un gestore eventi esegue in genere una delle azioni seguenti quando rileva un valore non valido:  
  
-   Fornisce automaticamente un valore noto da correggere, ad esempio il valore predefinito.  
  
-   Richiede informazioni all'utente del codice del server.  
  
-   Per gli eventi generati prima delle azioni associate, ad esempio <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> e <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, utilizza il <xref:System.ComponentModel.CancelEventArgs> argomento per annullare l'operazione.  
  
 Per altre informazioni sulla gestione degli eventi, vedere [Informazioni generali sui gestori eventi](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Le procedure seguenti viene illustrato come verificare la data di nascita valido utilizzando il <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> o <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> evento. Le procedure sono state scritte in base al presupposto che le impostazioni dell'applicazione siano già state create. In questo esempio, si eseguirà il controllo di un'impostazione denominata `DateOfBirth`. Per altre informazioni sulle impostazioni dell'applicazione, vedere [Procedura: Creare impostazioni applicazioni](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### <a name="to-obtain-the-application-settings-object"></a>Per ottenere l'oggetto delle impostazioni dell'applicazione  
  
-   Ottenere un riferimento all'oggetto delle impostazioni applicazione (l'istanza wrapper), completando uno degli elementi puntati seguenti:  
  
    -   Se le impostazioni sono state create usando la finestra di dialogo Impostazione applicazione di Visual Studio in **Editor proprietà**, è possibile recuperare l'oggetto predefinito delle impostazioni generato per la propria lingua tramite l'espressione seguente.  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         -oppure-  
  
    -   Se si è uno sviluppatore di Visual Basic e si sono create le impostazioni dell'applicazione tramite Creazione progetti, è possibile recuperare le impostazioni usando [My.Settings Object](~/docs/visual-basic/language-reference/objects/my-settings-object.md).  
  
         -oppure-  
  
    -   Se le impostazioni è stato creato mediante la derivazione da <xref:System.Configuration.ApplicationSettingsBase> direttamente, è necessario creare manualmente un'istanza della classe.  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 Sono state scritte le procedure seguenti presupponendo che l'oggetto impostazioni dell'applicazione sia stato ottenuto completando l'ultimo elemento puntato in questa procedura.  
  
### <a name="to-validate-application-settings-when-a-setting-is-changing"></a>Per convalidare le impostazioni dell'applicazione durante la modifica di un'impostazione  
  
1.  Se si è uno sviluppatore in c#, nel form o del controllo `Load` evento, aggiungere un gestore eventi per il <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> evento.  
  
     -oppure-  
  
     Se si è uno sviluppatore di Visual Basic, è necessario dichiarare la variabile `Settings` usando la parola chiave `WithEvents`.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingChanging += new SettingChangingEventHandler(MyCustomSettings_SettingChanging);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(sender as Object, e as EventArgs)  
        AddHandler settings.SettingChanging, AddressOf MyCustomSettings_SettingChanging  
    End Sub   
    ```  
  
2.  Definire il gestore eventi e scrivere il codice all'interno per eseguire il controllo associato alla data di nascita.  
  
    ```csharp  
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)  
    {  
        if (e.SettingName.Equals("DateOfBirth")) {  
            Date newDate = (Date)e.NewValue;  
            If (newDate > Date.Now) {  
                e.Cancel = true;  
                // Inform the user.  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingChanging(sender as Object, e as SettingChangingEventArgs) Handles Settings.SettingChanging  
        If (e.SettingName.Equals("DateOfBirth")) Then  
            Dim NewDate as Date = CType(e.NewValue, Date)  
            If (NewDate > Date.Now) Then  
                e.Cancel = True  
                ' Inform the user.  
            End If  
        End If  
    End Sub  
    ```  
  
### <a name="to-validate-application-settings-when-a-save-occurs"></a>Per convalidare le impostazioni applicazione durante un salvataggio  
  
1.  Nel form o del controllo `Load` evento, aggiungere un gestore eventi per il <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> evento.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingsSaving += new SettingsSavingEventHandler(MyCustomSettings_SettingsSaving);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(Sender as Object, e as EventArgs)  
        AddHandler settings.SettingsSaving, AddressOf MyCustomSettings_SettingsSaving  
    End Sub  
    ```  
  
2.  Definire il gestore eventi e scrivere il codice all'interno per eseguire il controllo associato alla data di nascita.  
  
    ```csharp  
    private void MyCustomSettings_SettingsSaving(Object sender, SettingsSavingEventArgs e)  
    {  
        if (this["DateOfBirth"] > Date.Now) {  
            e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingsSaving(Sender as Object, e as SettingsSavingEventArgs)  
        If (Me["DateOfBirth"] > Date.Now) Then  
            e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di gestori eventi in Windows Form](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Procedura: creare le impostazioni applicazione](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)
