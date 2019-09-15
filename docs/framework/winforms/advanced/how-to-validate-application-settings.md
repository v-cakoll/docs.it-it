---
title: 'Procedura: Convalidare le impostazioni applicazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
ms.openlocfilehash: b3b2447b570f0635942183dcc62c0e4ed73800d1
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972252"
---
# <a name="how-to-validate-application-settings"></a><span data-ttu-id="58217-102">Procedura: Convalidare le impostazioni applicazione</span><span class="sxs-lookup"><span data-stu-id="58217-102">How to: Validate Application Settings</span></span>

<span data-ttu-id="58217-103">In questo argomento viene illustrato come convalidare le impostazioni dell'applicazione prima dell'operazione che le rende persistenti.</span><span class="sxs-lookup"><span data-stu-id="58217-103">This topic demonstrates how to validate application settings before they are persisted.</span></span>

<span data-ttu-id="58217-104">Poiché le impostazioni dell'applicazione sono fortemente tipizzate, è necessario in qualche modo che gli utenti non possano assegnare dati di tipo non corretto a una determinata impostazione.</span><span class="sxs-lookup"><span data-stu-id="58217-104">Because application settings are strongly typed, you have some confidence that users cannot assign data of an incorrect type to a given setting.</span></span> <span data-ttu-id="58217-105">Un utente potrebbe comunque provare ad assegnare un valore a un'impostazione che non rientra nei limiti accettabili, ad esempio, fornendo una data di nascita che ha luogo nel futuro.</span><span class="sxs-lookup"><span data-stu-id="58217-105">However, a user still may attempt to assign a value to a setting that falls outside of acceptable bounds—for example, supplying a birth date that occurs in the future.</span></span> <span data-ttu-id="58217-106"><xref:System.Configuration.ApplicationSettingsBase>, la classe padre di tutte le classi di impostazioni dell'applicazione, espone quattro eventi per abilitare il controllo dei limiti.</span><span class="sxs-lookup"><span data-stu-id="58217-106"><xref:System.Configuration.ApplicationSettingsBase>, the parent class of all application settings classes, exposes four events to enable such bounds checking.</span></span> <span data-ttu-id="58217-107">La gestione di tali eventi inserisce tutto il codice di convalida in un'unica posizione, invece di distribuirlo in tutto il progetto.</span><span class="sxs-lookup"><span data-stu-id="58217-107">Handling these events puts all of your validation code in a single location, rather than scattering it throughout your project.</span></span>

<span data-ttu-id="58217-108">L'evento da usare dipende da quando è necessario convalidare le impostazioni, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="58217-108">The event you use depends upon when you need to validate your settings, as described in the following table.</span></span>

|<span data-ttu-id="58217-109">event</span><span class="sxs-lookup"><span data-stu-id="58217-109">Event</span></span>|<span data-ttu-id="58217-110">Occorrenza e uso</span><span class="sxs-lookup"><span data-stu-id="58217-110">Occurrence and use</span></span>|
|-----------|------------------------|
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|<span data-ttu-id="58217-111">Si verifica dopo il caricamento iniziale di un gruppo di proprietà delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="58217-111">Occurs after the initial loading of a settings property group.</span></span><br /><br /> <span data-ttu-id="58217-112">Usare questo evento per convalidare i valori iniziali per l'intero gruppo di proprietà prima che vengano usati all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58217-112">Use this event to validate initial values for the entire property group before they are used within the application.</span></span>|
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|<span data-ttu-id="58217-113">Si verifica prima che venga modificato il valore di una singola proprietà delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="58217-113">Occurs before the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="58217-114">Usare questo evento per convalidare una singola proprietà prima che venga modificata.</span><span class="sxs-lookup"><span data-stu-id="58217-114">Use this event to validate a single property before it is changed.</span></span> <span data-ttu-id="58217-115">Può offrire un feedback immediato agli utenti in relazione alle loro azioni e scelte.</span><span class="sxs-lookup"><span data-stu-id="58217-115">It can provide immediate feedback to users regarding their actions and choices.</span></span>|
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|<span data-ttu-id="58217-116">Si verifica quando viene modificato il valore di una singola proprietà delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="58217-116">Occurs after the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="58217-117">Usare questo evento per convalidare una singola proprietà dopo che è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="58217-117">Use this event to validate a single property after it is changed.</span></span> <span data-ttu-id="58217-118">Questo evento viene raramente usato per la convalida a meno che non sia necessario un lungo e asincrono processo di convalida.</span><span class="sxs-lookup"><span data-stu-id="58217-118">This event is rarely used for validation unless a lengthy, asynchronous validation process is required.</span></span>|
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|<span data-ttu-id="58217-119">Si verifica prima che il gruppo di impostazioni della proprietà venga archiviato.</span><span class="sxs-lookup"><span data-stu-id="58217-119">Occurs before the settings property group is stored.</span></span><br /><br /> <span data-ttu-id="58217-120">Usare questo evento per convalidare i valori per l'intero gruppo di proprietà prima che siano resi persistenti sul disco.</span><span class="sxs-lookup"><span data-stu-id="58217-120">Use this event to validate values for the entire property group before they are persisted to disk.</span></span>|

<span data-ttu-id="58217-121">In genere, non si usano tutti questi eventi all'interno della stessa applicazione ai fini della convalida.</span><span class="sxs-lookup"><span data-stu-id="58217-121">Typically, you will not use all of these events within the same application for validation purposes.</span></span> <span data-ttu-id="58217-122">Ad esempio, è spesso possibile soddisfare tutti i requisiti di convalida gestendo solo l' <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> evento.</span><span class="sxs-lookup"><span data-stu-id="58217-122">For example, it is often possible to fulfill all validation requirements by handling only the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>

<span data-ttu-id="58217-123">Un gestore eventi esegue in genere una delle azioni seguenti quando rileva un valore non valido:</span><span class="sxs-lookup"><span data-stu-id="58217-123">An event handler generally performs one of the following actions when it detects an invalid value:</span></span>

- <span data-ttu-id="58217-124">Fornisce automaticamente un valore noto da correggere, ad esempio il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="58217-124">Automatically supplies a value known to be correct, such as the default value.</span></span>

- <span data-ttu-id="58217-125">Richiede informazioni all'utente del codice del server.</span><span class="sxs-lookup"><span data-stu-id="58217-125">Re-queries the user of server code for information.</span></span>

- <span data-ttu-id="58217-126">Per gli eventi generati prima delle azioni associate, ad <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> esempio <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>e, USA <xref:System.ComponentModel.CancelEventArgs> l'argomento per annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="58217-126">For events raised before their associated actions, such as <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> and <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, uses the <xref:System.ComponentModel.CancelEventArgs> argument to cancel the operation.</span></span>

<span data-ttu-id="58217-127">Per altre informazioni sulla gestione degli eventi, vedere [Informazioni generali sui gestori eventi](../event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="58217-127">For more information about event handling, see [Event Handlers Overview](../event-handlers-overview-windows-forms.md).</span></span>

<span data-ttu-id="58217-128">Nelle procedure riportate di seguito viene illustrato come verificare una data di nascita <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> valida utilizzando <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> l'evento o.</span><span class="sxs-lookup"><span data-stu-id="58217-128">The following procedures show how to test for a valid birth date using either the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> or the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span> <span data-ttu-id="58217-129">Le procedure sono state scritte in base al presupposto che le impostazioni dell'applicazione siano già state create. In questo esempio, si eseguirà il controllo di un'impostazione denominata `DateOfBirth`.</span><span class="sxs-lookup"><span data-stu-id="58217-129">The procedures were written under the assumption that you have already created your application settings; in this example, we will perform bounds checking on a setting named `DateOfBirth`.</span></span> <span data-ttu-id="58217-130">Per ulteriori informazioni sulla creazione di impostazioni, [vedere Procedura: Creare le impostazioni](how-to-create-application-settings.md)dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58217-130">For more information about creating settings, see [How to: Create Application Settings](how-to-create-application-settings.md).</span></span>

### <a name="to-obtain-the-application-settings-object"></a><span data-ttu-id="58217-131">Per ottenere l'oggetto delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="58217-131">To obtain the application settings object</span></span>

- <span data-ttu-id="58217-132">Ottenere un riferimento all'oggetto delle impostazioni applicazione (l'istanza wrapper), completando uno degli elementi puntati seguenti:</span><span class="sxs-lookup"><span data-stu-id="58217-132">Obtain a reference to the application settings object (the wrapper instance) by completing one of the following bulleted items:</span></span>

  - <span data-ttu-id="58217-133">Se le impostazioni sono state create usando la finestra di dialogo Impostazione applicazione di Visual Studio in **Editor proprietà**, è possibile recuperare l'oggetto predefinito delle impostazioni generato per la propria lingua tramite l'espressione seguente.</span><span class="sxs-lookup"><span data-stu-id="58217-133">If you created your settings using the Visual Studio Application Settings dialog box in the **Property Editor**, you can retrieve the default settings object generated for your language through the following expression.</span></span>

    ```csharp
    Configuration.Settings.Default
    ```

    ```vb
    MySettings.Default
    ```

    <span data-ttu-id="58217-134">-oppure-</span><span class="sxs-lookup"><span data-stu-id="58217-134">-or-</span></span>

  - <span data-ttu-id="58217-135">Se si è uno sviluppatore di Visual Basic e si sono create le impostazioni dell'applicazione tramite Creazione progetti, è possibile recuperare le impostazioni usando [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="58217-135">If you are a Visual Basic developer and you created your application settings using the Project Designer, you can retrieve your settings by using the [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>

    <span data-ttu-id="58217-136">-oppure-</span><span class="sxs-lookup"><span data-stu-id="58217-136">-or-</span></span>

  - <span data-ttu-id="58217-137">Se le impostazioni sono state create derivando <xref:System.Configuration.ApplicationSettingsBase> direttamente da, è necessario creare un'istanza della classe manualmente.</span><span class="sxs-lookup"><span data-stu-id="58217-137">If you created your settings by deriving from <xref:System.Configuration.ApplicationSettingsBase> directly, you need to instantiate your class manually.</span></span>

    ```csharp
    MyCustomSettings settings = new MyCustomSettings();
    ```

    ```vb
    Dim Settings as New MyCustomSettings()
    ```

<span data-ttu-id="58217-138">Sono state scritte le procedure seguenti presupponendo che l'oggetto impostazioni dell'applicazione sia stato ottenuto completando l'ultimo elemento puntato in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="58217-138">The following procedures were written under the assumption that the application settings object was obtained by completing the last bulleted item in this procedure.</span></span>

### <a name="to-validate-application-settings-when-a-setting-is-changing"></a><span data-ttu-id="58217-139">Per convalidare le impostazioni dell'applicazione durante la modifica di un'impostazione</span><span class="sxs-lookup"><span data-stu-id="58217-139">To validate Application Settings when a setting is changing</span></span>

1. <span data-ttu-id="58217-140">Se si è uno C# sviluppatore, nell'evento del form o del `Load` controllo, aggiungere un gestore eventi per l' <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> evento.</span><span class="sxs-lookup"><span data-stu-id="58217-140">If you are a C# developer, in your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>

    <span data-ttu-id="58217-141">-oppure-</span><span class="sxs-lookup"><span data-stu-id="58217-141">-or-</span></span>

    <span data-ttu-id="58217-142">Se si è uno sviluppatore di Visual Basic, è necessario dichiarare la variabile `Settings` usando la parola chiave `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="58217-142">If you are a Visual Basic developer, you should declare the `Settings` variable using the `WithEvents` keyword.</span></span>

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

2. <span data-ttu-id="58217-143">Definire il gestore eventi e scrivere il codice all'interno per eseguire il controllo associato alla data di nascita.</span><span class="sxs-lookup"><span data-stu-id="58217-143">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>

    ```csharp
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)
    {
        if (e.SettingName.Equals("DateOfBirth"))
        {
            var newDate = (DateTime)e.NewValue;
            if (newDate > DateTime.Now)
            {
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

### <a name="to-validate-application-settings-when-a-save-occurs"></a><span data-ttu-id="58217-144">Per convalidare le impostazioni applicazione durante un salvataggio</span><span class="sxs-lookup"><span data-stu-id="58217-144">To validate Application Settings when a Save occurs</span></span>

1. <span data-ttu-id="58217-145">Nell'evento del form o del `Load` controllo, aggiungere un gestore eventi per l' <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> evento.</span><span class="sxs-lookup"><span data-stu-id="58217-145">In your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span>

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

2. <span data-ttu-id="58217-146">Definire il gestore eventi e scrivere il codice all'interno per eseguire il controllo associato alla data di nascita.</span><span class="sxs-lookup"><span data-stu-id="58217-146">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="58217-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58217-147">See also</span></span>

- [<span data-ttu-id="58217-148">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="58217-148">Creating Event Handlers in Windows Forms</span></span>](../creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="58217-149">Procedura: Crea impostazioni applicazione</span><span class="sxs-lookup"><span data-stu-id="58217-149">How to: Create Application Settings</span></span>](how-to-create-application-settings.md)
