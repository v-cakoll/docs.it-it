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
# <a name="how-to-validate-application-settings"></a><span data-ttu-id="4791d-102">Procedura: convalidare le impostazioni applicazione</span><span class="sxs-lookup"><span data-stu-id="4791d-102">How to: Validate Application Settings</span></span>
<span data-ttu-id="4791d-103">In questo argomento viene illustrato come convalidare le impostazioni dell'applicazione prima dell'operazione che le rende persistenti.</span><span class="sxs-lookup"><span data-stu-id="4791d-103">This topic demonstrates how to validate application settings before they are persisted.</span></span>  
  
 <span data-ttu-id="4791d-104">Poiché le impostazioni dell'applicazione sono fortemente tipizzate, è necessario in qualche modo che gli utenti non possano assegnare dati di tipo non corretto a una determinata impostazione.</span><span class="sxs-lookup"><span data-stu-id="4791d-104">Because application settings are strongly typed, you have some confidence that users cannot assign data of an incorrect type to a given setting.</span></span> <span data-ttu-id="4791d-105">Un utente potrebbe comunque provare ad assegnare un valore a un'impostazione che non rientra nei limiti accettabili, ad esempio, fornendo una data di nascita che ha luogo nel futuro.</span><span class="sxs-lookup"><span data-stu-id="4791d-105">However, a user still may attempt to assign a value to a setting that falls outside of acceptable bounds—for example, supplying a birth date that occurs in the future.</span></span> <span data-ttu-id="4791d-106"><xref:System.Configuration.ApplicationSettingsBase>, la classe padre di tutte le classi di impostazioni applicazione, espone quattro eventi da abilitare tali controllo dei limiti.</span><span class="sxs-lookup"><span data-stu-id="4791d-106"><xref:System.Configuration.ApplicationSettingsBase>, the parent class of all application settings classes, exposes four events to enable such bounds checking.</span></span> <span data-ttu-id="4791d-107">La gestione di tali eventi inserisce tutto il codice di convalida in un'unica posizione, invece di distribuirlo in tutto il progetto.</span><span class="sxs-lookup"><span data-stu-id="4791d-107">Handling these events puts all of your validation code in a single location, rather than scattering it throughout your project.</span></span>  
  
 <span data-ttu-id="4791d-108">L'evento da usare dipende da quando è necessario convalidare le impostazioni, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4791d-108">The event you use depends upon when you need to validate your settings, as described in the following table.</span></span>  
  
|<span data-ttu-id="4791d-109">Evento</span><span class="sxs-lookup"><span data-stu-id="4791d-109">Event</span></span>|<span data-ttu-id="4791d-110">Occorrenza e uso</span><span class="sxs-lookup"><span data-stu-id="4791d-110">Occurrence and use</span></span>|  
|-----------|------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|<span data-ttu-id="4791d-111">Si verifica dopo il caricamento iniziale di un gruppo di proprietà delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4791d-111">Occurs after the initial loading of a settings property group.</span></span><br /><br /> <span data-ttu-id="4791d-112">Usare questo evento per convalidare i valori iniziali per l'intero gruppo di proprietà prima che vengano usati all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4791d-112">Use this event to validate initial values for the entire property group before they are used within the application.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|<span data-ttu-id="4791d-113">Si verifica prima che venga modificato il valore di una singola proprietà delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4791d-113">Occurs before the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="4791d-114">Usare questo evento per convalidare una singola proprietà prima che venga modificata.</span><span class="sxs-lookup"><span data-stu-id="4791d-114">Use this event to validate a single property before it is changed.</span></span> <span data-ttu-id="4791d-115">Può offrire un feedback immediato agli utenti in relazione alle loro azioni e scelte.</span><span class="sxs-lookup"><span data-stu-id="4791d-115">It can provide immediate feedback to users regarding their actions and choices.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|<span data-ttu-id="4791d-116">Si verifica quando viene modificato il valore di una singola proprietà delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4791d-116">Occurs after the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="4791d-117">Usare questo evento per convalidare una singola proprietà dopo che è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="4791d-117">Use this event to validate a single property after it is changed.</span></span> <span data-ttu-id="4791d-118">Questo evento viene raramente usato per la convalida a meno che non sia necessario un lungo e asincrono processo di convalida.</span><span class="sxs-lookup"><span data-stu-id="4791d-118">This event is rarely used for validation unless a lengthy, asynchronous validation process is required.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|<span data-ttu-id="4791d-119">Si verifica prima che il gruppo di impostazioni della proprietà venga archiviato.</span><span class="sxs-lookup"><span data-stu-id="4791d-119">Occurs before the settings property group is stored.</span></span><br /><br /> <span data-ttu-id="4791d-120">Usare questo evento per convalidare i valori per l'intero gruppo di proprietà prima che siano resi persistenti sul disco.</span><span class="sxs-lookup"><span data-stu-id="4791d-120">Use this event to validate values for the entire property group before they are persisted to disk.</span></span>|  
  
 <span data-ttu-id="4791d-121">In genere, non si usano tutti questi eventi all'interno della stessa applicazione ai fini della convalida.</span><span class="sxs-lookup"><span data-stu-id="4791d-121">Typically, you will not use all of these events within the same application for validation purposes.</span></span> <span data-ttu-id="4791d-122">Ad esempio, è possibile soddisfare tutti i requisiti di convalida gestendo solo il <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> evento.</span><span class="sxs-lookup"><span data-stu-id="4791d-122">For example, it is often possible to fulfill all validation requirements by handling only the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
 <span data-ttu-id="4791d-123">Un gestore eventi esegue in genere una delle azioni seguenti quando rileva un valore non valido:</span><span class="sxs-lookup"><span data-stu-id="4791d-123">An event handler generally performs one of the following actions when it detects an invalid value:</span></span>  
  
-   <span data-ttu-id="4791d-124">Fornisce automaticamente un valore noto da correggere, ad esempio il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4791d-124">Automatically supplies a value known to be correct, such as the default value.</span></span>  
  
-   <span data-ttu-id="4791d-125">Richiede informazioni all'utente del codice del server.</span><span class="sxs-lookup"><span data-stu-id="4791d-125">Re-queries the user of server code for information.</span></span>  
  
-   <span data-ttu-id="4791d-126">Per gli eventi generati prima delle azioni associate, ad esempio <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> e <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, utilizza il <xref:System.ComponentModel.CancelEventArgs> argomento per annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="4791d-126">For events raised before their associated actions, such as <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> and <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, uses the <xref:System.ComponentModel.CancelEventArgs> argument to cancel the operation.</span></span>  
  
 <span data-ttu-id="4791d-127">Per altre informazioni sulla gestione degli eventi, vedere [Informazioni generali sui gestori eventi](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4791d-127">For more information about event handling, see [Event Handlers Overview](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="4791d-128">Le procedure seguenti viene illustrato come verificare la data di nascita valido utilizzando il <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> o <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> evento.</span><span class="sxs-lookup"><span data-stu-id="4791d-128">The following procedures show how to test for a valid birth date using either the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> or the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span> <span data-ttu-id="4791d-129">Le procedure sono state scritte in base al presupposto che le impostazioni dell'applicazione siano già state create. In questo esempio, si eseguirà il controllo di un'impostazione denominata `DateOfBirth`.</span><span class="sxs-lookup"><span data-stu-id="4791d-129">The procedures were written under the assumption that you have already created your application settings; in this example, we will perform bounds checking on a setting named `DateOfBirth`.</span></span> <span data-ttu-id="4791d-130">Per altre informazioni sulle impostazioni dell'applicazione, vedere [Procedura: Creare impostazioni applicazioni](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4791d-130">For more information about creating settings, see [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span></span>  
  
### <a name="to-obtain-the-application-settings-object"></a><span data-ttu-id="4791d-131">Per ottenere l'oggetto delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="4791d-131">To obtain the application settings object</span></span>  
  
-   <span data-ttu-id="4791d-132">Ottenere un riferimento all'oggetto delle impostazioni applicazione (l'istanza wrapper), completando uno degli elementi puntati seguenti:</span><span class="sxs-lookup"><span data-stu-id="4791d-132">Obtain a reference to the application settings object (the wrapper instance) by completing one of the following bulleted items:</span></span>  
  
    -   <span data-ttu-id="4791d-133">Se le impostazioni sono state create usando la finestra di dialogo Impostazione applicazione di Visual Studio in **Editor proprietà**, è possibile recuperare l'oggetto predefinito delle impostazioni generato per la propria lingua tramite l'espressione seguente.</span><span class="sxs-lookup"><span data-stu-id="4791d-133">If you created your settings using the Visual Studio Application Settings dialog box in the **Property Editor**, you can retrieve the default settings object generated for your language through the following expression.</span></span>  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         <span data-ttu-id="4791d-134">-oppure-</span><span class="sxs-lookup"><span data-stu-id="4791d-134">-or-</span></span>  
  
    -   <span data-ttu-id="4791d-135">Se si è uno sviluppatore di Visual Basic e si sono create le impostazioni dell'applicazione tramite Creazione progetti, è possibile recuperare le impostazioni usando [My.Settings Object](~/docs/visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="4791d-135">If you are a Visual Basic developer and you created your application settings using the Project Designer, you can retrieve your settings by using the [My.Settings Object](~/docs/visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
         <span data-ttu-id="4791d-136">-oppure-</span><span class="sxs-lookup"><span data-stu-id="4791d-136">-or-</span></span>  
  
    -   <span data-ttu-id="4791d-137">Se le impostazioni è stato creato mediante la derivazione da <xref:System.Configuration.ApplicationSettingsBase> direttamente, è necessario creare manualmente un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="4791d-137">If you created your settings by deriving from <xref:System.Configuration.ApplicationSettingsBase> directly, you need to instantiate your class manually.</span></span>  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 <span data-ttu-id="4791d-138">Sono state scritte le procedure seguenti presupponendo che l'oggetto impostazioni dell'applicazione sia stato ottenuto completando l'ultimo elemento puntato in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4791d-138">The following procedures were written under the assumption that the application settings object was obtained by completing the last bulleted item in this procedure.</span></span>  
  
### <a name="to-validate-application-settings-when-a-setting-is-changing"></a><span data-ttu-id="4791d-139">Per convalidare le impostazioni dell'applicazione durante la modifica di un'impostazione</span><span class="sxs-lookup"><span data-stu-id="4791d-139">To validate Application Settings when a setting is changing</span></span>  
  
1.  <span data-ttu-id="4791d-140">Se si è uno sviluppatore in c#, nel form o del controllo `Load` evento, aggiungere un gestore eventi per il <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> evento.</span><span class="sxs-lookup"><span data-stu-id="4791d-140">If you are a C# developer, in your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
     <span data-ttu-id="4791d-141">-oppure-</span><span class="sxs-lookup"><span data-stu-id="4791d-141">-or-</span></span>  
  
     <span data-ttu-id="4791d-142">Se si è uno sviluppatore di Visual Basic, è necessario dichiarare la variabile `Settings` usando la parola chiave `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="4791d-142">If you are a Visual Basic developer, you should declare the `Settings` variable using the `WithEvents` keyword.</span></span>  
  
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
  
2.  <span data-ttu-id="4791d-143">Definire il gestore eventi e scrivere il codice all'interno per eseguire il controllo associato alla data di nascita.</span><span class="sxs-lookup"><span data-stu-id="4791d-143">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
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
  
### <a name="to-validate-application-settings-when-a-save-occurs"></a><span data-ttu-id="4791d-144">Per convalidare le impostazioni applicazione durante un salvataggio</span><span class="sxs-lookup"><span data-stu-id="4791d-144">To validate Application Settings when a Save occurs</span></span>  
  
1.  <span data-ttu-id="4791d-145">Nel form o del controllo `Load` evento, aggiungere un gestore eventi per il <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> evento.</span><span class="sxs-lookup"><span data-stu-id="4791d-145">In your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span>  
  
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
  
2.  <span data-ttu-id="4791d-146">Definire il gestore eventi e scrivere il codice all'interno per eseguire il controllo associato alla data di nascita.</span><span class="sxs-lookup"><span data-stu-id="4791d-146">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4791d-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4791d-147">See Also</span></span>  
 [<span data-ttu-id="4791d-148">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4791d-148">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="4791d-149">Procedura: creare le impostazioni applicazione</span><span class="sxs-lookup"><span data-stu-id="4791d-149">How to: Create Application Settings</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)
