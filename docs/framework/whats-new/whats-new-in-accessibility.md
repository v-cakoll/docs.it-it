---
title: "Nuove funzionalità di accessibilità in .NET Framework"
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6a6759ae285f2dd101bddf71ea8e5ca792e87df
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="0b71a-102">Nuove funzionalità di accessibilità in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0b71a-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="0b71a-103">Uno degli obiettivi di .NET Framework è rendere le applicazioni più accessibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0b71a-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="0b71a-104">Le funzionalità di accessibilità consentono a un'applicazione di offrire un'esperienza appropriata per gli utenti di assistive technology.</span><span class="sxs-lookup"><span data-stu-id="0b71a-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="0b71a-105">A partire da .NET Framework 4.7.1, .NET Framework include numerosi miglioramenti per l'accessibilità che consentono agli sviluppatori di creare applicazioni accessibili.</span><span class="sxs-lookup"><span data-stu-id="0b71a-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="0b71a-106">Le nuove funzionalità di accessibilità sono abilitate per impostazione predefinita per le applicazioni destinate a .NET Framework 4.7.1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0b71a-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="0b71a-107">Inoltre, le applicazioni destinate a una versione precedente di .NET Framework, ma eseguite in .NET Framework 4.7.1 o versioni successive possono rifiutare in modo esplicito comportamenti di accessibilità legacy (accettando quindi i miglioramenti per l'accessibilità in .NET Framework 4.7.1) aggiungendo l'opzione seguente all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0b71a-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="0b71a-108">Analogamente, le applicazioni destinate alle versioni di .NET Framework a partire da 4.7.1 possono disabilitare le funzionalità di accessibilità aggiungendo la seguente opzione all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0b71a-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="0b71a-109">Nuove funzionalità di accessibilità in .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="0b71a-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="0b71a-110">.NET Framework 4.7.1 include nuove funzionalità di accessibilità nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b71a-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="0b71a-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="0b71a-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="0b71a-112">Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b71a-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="0b71a-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="0b71a-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="0b71a-114">**Miglioramenti per le utilità per la lettura dello schermo**</span><span class="sxs-lookup"><span data-stu-id="0b71a-114">**Screen reader improvements**</span></span>

<span data-ttu-id="0b71a-115">Se sono abilitati i miglioramenti per l'accessibilità, .NET Framework 4.7.1 include i miglioramenti seguenti che riguardano le utilità per la lettura dello schermo:</span><span class="sxs-lookup"><span data-stu-id="0b71a-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="0b71a-116">In .NET Framework 4.7 e versioni precedenti, i controlli <xref:System.Windows.Controls.Expander> vengono annunciati come pulsanti dalle utilità per la lettura dello schermo.</span><span class="sxs-lookup"><span data-stu-id="0b71a-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="0b71a-117">A partire da .NET Framework 4.7.1, sono annunciati correttamente come gruppi espandibili/comprimibili.</span><span class="sxs-lookup"><span data-stu-id="0b71a-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="0b71a-118">In .NET Framework 4.7 e versioni precedenti, i controlli <xref:System.Windows.Controls.DataGridCell> vengono annunciati come "personalizzati".</span><span class="sxs-lookup"><span data-stu-id="0b71a-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="0b71a-119">A partire da .NET Framework 4.7.1, sono annunciati correttamente come cella di griglia dati (localizzati).</span><span class="sxs-lookup"><span data-stu-id="0b71a-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="0b71a-120">A partire da .NET Framework 4.7.1, le utilità per la lettura dello schermo annunciano il nome di un controllo <xref:System.Windows.Controls.ComboBox> modificabile.</span><span class="sxs-lookup"><span data-stu-id="0b71a-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="0b71a-121">In .NET Framework 4.7 e versioni precedenti, i controlli <xref:System.Windows.Controls.PasswordBox> vengono annunciati come "Nessun elemento visualizzato" o il comportamento è in altro modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="0b71a-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="0b71a-122">Questo problema è stato risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="0b71a-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="0b71a-123">**Supporto di aree dinamiche UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="0b71a-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="0b71a-124">Le utilità per la lettura dello schermo, come Assistente vocale, consentono di leggere il contenuto dell'interfaccia utente di un'applicazione, in genere annunciando tramite sintesi vocale il contenuto dell'interfaccia utente con lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0b71a-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="0b71a-125">Tuttavia, se un elemento dell'interfaccia utente viene modificato e non ha lo stato attivo, l'utente potrebbe non ricevere notifica e perdere informazioni importanti.</span><span class="sxs-lookup"><span data-stu-id="0b71a-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="0b71a-126">Le aree dinamiche sono progettate per risolvere questo problema.</span><span class="sxs-lookup"><span data-stu-id="0b71a-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="0b71a-127">Uno sviluppatore può usarle per informare l'utilità per la lettura dello schermo o qualsiasi altro client UIAutomation di un'importante modifica apportata a un elemento dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0b71a-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="0b71a-128">L'utilità per la lettura dello schermo può quindi decidere come e quando informare l'utente di questa modifica.</span><span class="sxs-lookup"><span data-stu-id="0b71a-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="0b71a-129">Per supportare le aree dinamiche sono state aggiunte le API seguenti a WPF:</span><span class="sxs-lookup"><span data-stu-id="0b71a-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="0b71a-130">I campi <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> che identificano la proprietà **LiveSetting** e l'evento **LiveRegionChanged**.</span><span class="sxs-lookup"><span data-stu-id="0b71a-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="0b71a-131">Questi campi possono essere impostati tramite XAML.</span><span class="sxs-lookup"><span data-stu-id="0b71a-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="0b71a-132">La proprietà associata **AutomationProperties.LiveSetting**, che segnala all'utilità per la lettura dello schermo l'importanza della modifica dell'interfaccia utente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0b71a-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="0b71a-133">La proprietà <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, che identifica la proprietà associata **AutomationProperties.LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="0b71a-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="0b71a-134">Il metodo <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, di cui è possibile eseguire l'override per specificare un valore **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="0b71a-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="0b71a-135">I metodi <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, che consentono di ottenere e impostare un valore **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="0b71a-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="0b71a-136">L'enumerazione <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, che definisce le i valori **LiveSetting** possibili seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b71a-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="0b71a-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b71a-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0b71a-138">L'elemento non invia notifiche se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="0b71a-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="0b71a-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b71a-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0b71a-140">L'elemento invia notifiche che non causano interruzioni se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="0b71a-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="0b71a-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b71a-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0b71a-142">L'elemento invia notifiche con interruzioni se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="0b71a-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="0b71a-143">È possibile creare un'area dinamica impostando la proprietà **AutomationProperties.LiveSetting** sull'elemento di interesse, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0b71a-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="0b71a-144">Quando vengono modificati i dati nell'area dinamica ed è necessario informarne un'utilità per la lettura dello schermo, deve essere generato un evento in modo esplicito, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0b71a-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="0b71a-145">**Contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="0b71a-145">**High contrast**</span></span>

<span data-ttu-id="0b71a-146">A partire da .NET Framework 4.7.1, sono stati apportati miglioramenti relativi al contrasto elevato per vari controlli WPF,</span><span class="sxs-lookup"><span data-stu-id="0b71a-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="0b71a-147">che sono ora visibili quando viene impostato il tema <xref:System.Windows.SystemParameters.HighContrast%2A>.</span><span class="sxs-lookup"><span data-stu-id="0b71a-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="0b71a-148">Sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="0b71a-148">These include:</span></span>

- <span data-ttu-id="0b71a-149">Controllo <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="0b71a-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="0b71a-150">L'oggetto visivo per lo stato attivo per il controllo <xref:System.Windows.Controls.Expander> è ora visibile.</span><span class="sxs-lookup"><span data-stu-id="0b71a-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="0b71a-151">Anche gli oggetti visivi della tastiera per i controlli <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.RadioButton> sono visibili.</span><span class="sxs-lookup"><span data-stu-id="0b71a-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="0b71a-152">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0b71a-152">For example:</span></span>

    <span data-ttu-id="0b71a-153">Prima:</span><span class="sxs-lookup"><span data-stu-id="0b71a-153">Before:</span></span> 
    
    ![Controllo Expander con lo stato attivo prima dei miglioramenti per l'accessibilità](media/expander-before.png)

    <span data-ttu-id="0b71a-155">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0b71a-155">After:</span></span> 

    ![Controllo Expander con lo stato attivo dopo i miglioramenti per l'accessibilità](media/expander-after.png)

- <span data-ttu-id="0b71a-157">Controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton></span><span class="sxs-lookup"><span data-stu-id="0b71a-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="0b71a-158">Il testo nei controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton> è ora più semplice da vedere quando viene selezionato nei temi a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="0b71a-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="0b71a-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0b71a-159">For example:</span></span>

    <span data-ttu-id="0b71a-160">Prima:</span><span class="sxs-lookup"><span data-stu-id="0b71a-160">Before:</span></span> 

    ![Pulsante di opzione con contrasto elevato con lo stato attivo prima dei miglioramenti per l'accessibilità](media/radio-button-before.png)
    
    <span data-ttu-id="0b71a-162">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0b71a-162">After:</span></span> 

    ![Pulsante di opzione con contrasto elevato con lo stato attivo dopo i miglioramenti per l'accessibilità](media/radio-button-after.png)

- <span data-ttu-id="0b71a-164">Controllo <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="0b71a-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="0b71a-165">A partire da .NET Framework 4.7.1, il bordo di un controllo <xref:System.Windows.Controls.ComboBox> disabilitato ha lo stesso colore del testo disabilitato.</span><span class="sxs-lookup"><span data-stu-id="0b71a-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="0b71a-166">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0b71a-166">For example:</span></span>
    
    <span data-ttu-id="0b71a-167">Prima:</span><span class="sxs-lookup"><span data-stu-id="0b71a-167">Before:</span></span> 

     ![Bordo e testo disabilitati del controllo ComboBox prima dei miglioramenti per l'accessibilità](media/combo-disabled-before.png)

    <span data-ttu-id="0b71a-169">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0b71a-169">After:</span></span>   

     ![Bordo e testo disabilitati del controllo ComboBox dopo i miglioramenti per l'accessibilità](media/combo-disabled-after.png)

    <span data-ttu-id="0b71a-171">Inoltre, i pulsanti con lo stato attivo e disabilitati usano il colore del tema corretto.</span><span class="sxs-lookup"><span data-stu-id="0b71a-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="0b71a-172">Prima:</span><span class="sxs-lookup"><span data-stu-id="0b71a-172">Before:</span></span>

    ![Colori del tema dei pulsanti prima dei miglioramenti per l'accessibilità](media/button-themes-before.png) 
    
    <span data-ttu-id="0b71a-174">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0b71a-174">After:</span></span> 

    ![Colori del tema dei pulsanti dopo i miglioramenti per l'accessibilità](media/button-themes-after.png) 

    <span data-ttu-id="0b71a-176">Infine, in .NET Framework 4.7 e versioni precedenti, l'impostazione dello stile di un controllo <xref:System.Windows.Controls.ComboBox> su `Toolbar.ComboBoxStyleKey` rende invisibile la freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="0b71a-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="0b71a-177">Questo problema è stato risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="0b71a-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="0b71a-178">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0b71a-178">For example:</span></span>

    <span data-ttu-id="0b71a-179">Prima:</span><span class="sxs-lookup"><span data-stu-id="0b71a-179">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey prima dei miglioramenti per l'accessibilità](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="0b71a-181">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0b71a-181">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey dopo i miglioramenti per l'accessibilità](media/comboboxstylekey-after.png) 

- <span data-ttu-id="0b71a-183">Controllo <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="0b71a-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="0b71a-184">A partire da .NET Framework 4.7.1, la freccia dell'indicatore di ordinamento nei controlli <xref:System.Windows.Controls.DataGrid> usa ora i colori del tema corretti.</span><span class="sxs-lookup"><span data-stu-id="0b71a-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="0b71a-185">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0b71a-185">For example:</span></span>

    <span data-ttu-id="0b71a-186">Prima:</span><span class="sxs-lookup"><span data-stu-id="0b71a-186">Before:</span></span> 

    ![Freccia dell'indicatore di ordinamento prima dei miglioramenti per l'accessibilità](media/sort-indicator-before.png) 
    
    <span data-ttu-id="0b71a-188">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0b71a-188">After:</span></span>   
 
    ![Freccia dell'indicatore di ordinamento dopo i miglioramenti per l'accessibilità](media/sort-indicator-after.png) 
    
    <span data-ttu-id="0b71a-190">Inoltre, in .NET Framework 4.7 e versioni precedenti, per lo stile di collegamento predefinito viene usato un colore non corretto al passaggio del mouse in modalità a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="0b71a-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="0b71a-191">Questo problema è stato risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="0b71a-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="0b71a-192">Analogamente, le colonne della casella di controllo per i controlli <xref:System.Windows.Controls.DataGrid> usano i colori previsti per il riscontro dello stato attivo della tastiera a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="0b71a-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="0b71a-193">Prima:</span><span class="sxs-lookup"><span data-stu-id="0b71a-193">Before:</span></span> 

    ![Stile di collegamento predefinito DataGrid prima dei miglioramenti per l'accessibilità](media/default-link-style-before.png) 
 
    <span data-ttu-id="0b71a-195">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0b71a-195">After:</span></span>    
  
    ![Stile di collegamento predefinito DataGrid dopo i miglioramenti per l'accessibilità](media/default-link-style-after.png)  

<span data-ttu-id="0b71a-197">Per altre informazioni sui miglioramenti per l'accessibilità di WPF in .NET Framework 4.7.1, vedere [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf) (Miglioramenti per l'accessibilità in WPF).</span><span class="sxs-lookup"><span data-stu-id="0b71a-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="0b71a-198">Miglioramenti per l'accessibilità di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b71a-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="0b71a-199">In .NET Framework 4.7.1 Windows Form (WinForms) include modifiche per l'accessibilità nelle aree seguenti.</span><span class="sxs-lookup"><span data-stu-id="0b71a-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="0b71a-200">**Miglioramento della visualizzazione in modalità a contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="0b71a-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="0b71a-201">A partire da .NET Framework 4.7.1, vari controlli WinForms offrono un rendering migliorato nelle modalità a contrasto elevato disponibili nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0b71a-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="0b71a-202">Windows 10 ha cambiato i valori di alcuni colori di sistema a contrasto elevato e Windows Form si basa sul framework Win32 di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0b71a-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="0b71a-203">Per risultati ottimali, usare la versione più recente di Windows e accettare le modifiche del sistema operativo più recenti aggiungendo un file app.manifest in un'applicazione di test e rimuovere il commento dalla riga del sistema operativo supportato Windows 10, in modo che sia come segue:</span><span class="sxs-lookup"><span data-stu-id="0b71a-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="0b71a-204">Alcuni esempi di modifiche per il contrasto elevato includono:</span><span class="sxs-lookup"><span data-stu-id="0b71a-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="0b71a-205">I segni di spunta negli elementi <xref:System.Windows.Forms.MenuStrip> sono più facili da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="0b71a-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="0b71a-206">Gli elementi <xref:System.Windows.Forms.MenuStrip> disabilitati sono più facili da visualizzare quando sono selezionati.</span><span class="sxs-lookup"><span data-stu-id="0b71a-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="0b71a-207">Il testo in un controllo <xref:System.Windows.Forms.Button> selezionato è contrastato rispetto al colore della selezione.</span><span class="sxs-lookup"><span data-stu-id="0b71a-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="0b71a-208">Il testo disabilitato è più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="0b71a-208">Disabled text is easier to read.</span></span> <span data-ttu-id="0b71a-209">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0b71a-209">For example:</span></span>

    <span data-ttu-id="0b71a-210">Prima:</span><span class="sxs-lookup"><span data-stu-id="0b71a-210">Before:</span></span>

    ![Testo disabilitato prima dei miglioramenti per l'accessibilità](media/wf-disabled-before.png) 

    <span data-ttu-id="0b71a-212">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0b71a-212">After:</span></span>

    ![Testo disabilitato dopo i miglioramenti per l'accessibilità](media/wf-disabled-after.png) 

- <span data-ttu-id="0b71a-214">Miglioramenti per il contrasto elevato nella finestra di dialogo di eccezione del thread.</span><span class="sxs-lookup"><span data-stu-id="0b71a-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="0b71a-215">**Supporto migliorato di Assistente vocale**</span><span class="sxs-lookup"><span data-stu-id="0b71a-215">**Improved Narrator support**</span></span>

<span data-ttu-id="0b71a-216">Windows Form in .NET Framework 4.7.1 include i seguenti miglioramenti per l'accessibilità per l'Assistente vocale:</span><span class="sxs-lookup"><span data-stu-id="0b71a-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="0b71a-217">Il controllo <xref:System.Windows.Forms.MonthCalendar> è accessibile per l'Assistente vocale, così come da altri strumenti di automazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0b71a-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="0b71a-218">Il controllo <xref:System.Windows.Forms.CheckedListBox> segnala all'Assistente vocale lo stato di selezione di un elemento, in modo che l'utente riceva notifica della modifica del valore di un elemento di elenco.</span><span class="sxs-lookup"><span data-stu-id="0b71a-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="0b71a-219">Il controllo <xref:System.Windows.Forms.DataGridViewCell> segnala lo stato di sola lettura corretto all'Assistente vocale.</span><span class="sxs-lookup"><span data-stu-id="0b71a-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="0b71a-220">Assistente vocale può ora leggere il testo <xref:System.Windows.Forms.ToolStripMenuItem> disabilitato, mentre in precedenza ignorava le voci di menu disabilitate.</span><span class="sxs-lookup"><span data-stu-id="0b71a-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="0b71a-221">**Supporto avanzato per i modelli di accessibilità UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="0b71a-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="0b71a-222">A partire da .NET Framework 4.7.1, gli sviluppatori di strumenti di tecnologia per l'accessibilità possono sfruttare i modelli e le proprietà di accessibilità delle API comuni per numerosi controlli WinForms.</span><span class="sxs-lookup"><span data-stu-id="0b71a-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="0b71a-223">Questi miglioramenti per l'accessibilità includono:</span><span class="sxs-lookup"><span data-stu-id="0b71a-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="0b71a-224"><xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ToolStripSplitButton> ora supportano il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="0b71a-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="0b71a-225"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> supporta ora il [modello di attivazione/disattivazione](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="0b71a-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="0b71a-226">Il controllo <xref:System.Windows.Forms.ToolStripItem> supporta la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> e il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="0b71a-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="0b71a-227">I controlli <xref:System.Windows.Forms.NumericUpDown> e <xref:System.Windows.Forms.DomainUpDown> supportano la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.</span><span class="sxs-lookup"><span data-stu-id="0b71a-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="0b71a-228">**Esperienza migliorata per il visualizzatore proprietà**</span><span class="sxs-lookup"><span data-stu-id="0b71a-228">**Improved property browser experience**</span></span>

<span data-ttu-id="0b71a-229">A partire da .NET Framework 4.7.1, Windows Form include:</span><span class="sxs-lookup"><span data-stu-id="0b71a-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="0b71a-230">Migliori spostamenti tramite tastiera tra le varie finestre di selezione a discesa.</span><span class="sxs-lookup"><span data-stu-id="0b71a-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="0b71a-231">Riduzione dei punti di tabulazione non necessari.</span><span class="sxs-lookup"><span data-stu-id="0b71a-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="0b71a-232">Segnalazione migliore dei tipi di controllo.</span><span class="sxs-lookup"><span data-stu-id="0b71a-232">Better reporting of control types.</span></span>
- <span data-ttu-id="0b71a-233">Comportamento migliorato dell'Assistente vocale.</span><span class="sxs-lookup"><span data-stu-id="0b71a-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="0b71a-234">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b71a-234">See Also</span></span>
[<span data-ttu-id="0b71a-235">Novità di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0b71a-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 