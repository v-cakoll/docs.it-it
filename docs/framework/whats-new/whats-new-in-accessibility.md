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
ms.openlocfilehash: 4886dad94d3a67e78525241a1538c06b9fe4b0be
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2017
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="1501a-102">Nuove funzionalità di accessibilità in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1501a-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="1501a-103">.NET Framework mira a rendere le applicazioni più accessibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1501a-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="1501a-104">Funzionalità di accessibilità consentono di offrire un'esperienza appropriata per gli utenti di Assistive Technology.</span><span class="sxs-lookup"><span data-stu-id="1501a-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="1501a-105">A partire da .NET Framework 4.7.1, .NET Framework include un numero elevato di miglioramenti di accessibilità che consentono agli sviluppatori di creare applicazioni di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="1501a-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="1501a-106">Le nuove funzionalità di accessibilità sono abilitati per impostazione predefinita per le applicazioni destinate a .NET Framework 4.7.1 o successive.</span><span class="sxs-lookup"><span data-stu-id="1501a-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="1501a-107">Inoltre, applicazioni di destinazione una versione precedente di .NET Framework, ma sono in esecuzione in .NET Framework 4.7.1 o versioni successive è possono scegliere di comportamenti di accessibilità legacy (e in tal modo optare per i miglioramenti di accessibilità in .NET Framework 4.7.1) da aggiungendo il seguente parametro per il [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento il [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1501a-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="1501a-108">Analogamente, le applicazioni destinate alle versioni di .NET Framework a partire da 4.7.1 possono disabilitare le funzionalità di accessibilità aggiungendo la seguente opzione per il [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento il [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1501a-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="1501a-109">Nuove funzionalità di accessibilità in .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="1501a-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="1501a-110">.NET Framework 4.7.1 include nuove funzionalità di accessibilità nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="1501a-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="1501a-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="1501a-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="1501a-112">Windows Form</span><span class="sxs-lookup"><span data-stu-id="1501a-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="1501a-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="1501a-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="1501a-114">**Miglioramenti di lettura dello schermo**</span><span class="sxs-lookup"><span data-stu-id="1501a-114">**Screen reader improvements**</span></span>

<span data-ttu-id="1501a-115">Se sono abilitati i miglioramenti di accessibilità, .NET Framework 4.7.1 include i miglioramenti seguenti che interessano gli screen reader:</span><span class="sxs-lookup"><span data-stu-id="1501a-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="1501a-116">In .NET Framework 4.7 e versioni precedenti, <xref:System.Windows.Controls.Expander> controlli annunciati lettura dello schermo come pulsanti.</span><span class="sxs-lookup"><span data-stu-id="1501a-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="1501a-117">A partire da .NET Framework 4.7.1, sono correttamente annunciati come gruppi espandibile/comprimibile.</span><span class="sxs-lookup"><span data-stu-id="1501a-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="1501a-118">In .NET Framework 4.7 e versioni precedenti, <xref:System.Windows.Controls.DataGridCell> controlli annunciati lettura dello schermo come "custom".</span><span class="sxs-lookup"><span data-stu-id="1501a-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="1501a-119">A partire da .NET Framework 4.7.1, sono ora correttamente annunciati come cella della griglia di dati (localizzato).</span><span class="sxs-lookup"><span data-stu-id="1501a-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="1501a-120">A partire da .NET Framework 4.7.1, gli screen reader annunciare il nome di un modificabile <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="1501a-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="1501a-121">In .NET Framework 4.7 e versioni precedenti, <xref:System.Windows.Controls.PasswordBox> controlli sono stati annunciati come "Nessun elemento nella vista" o ha un comportamento in caso contrario non corretto.</span><span class="sxs-lookup"><span data-stu-id="1501a-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="1501a-122">Questo problema è risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="1501a-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="1501a-123">**Supporto UIAutomation LiveRegion**</span><span class="sxs-lookup"><span data-stu-id="1501a-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="1501a-124">Lettura dello schermo, ad esempio persone Guida Assistente vocale legge il contenuto dell'interfaccia utente di un'applicazione, in genere dall'output di sintesi vocale del contenuto dell'interfaccia utente che ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="1501a-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="1501a-125">Tuttavia, se un elemento dell'interfaccia utente viene modificato e non ha lo stato attivo, l'utente non può essere comunicata e potrebbe non essere implementato informazioni importanti.</span><span class="sxs-lookup"><span data-stu-id="1501a-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="1501a-126">Le aree in tempo reale hanno lo scopo di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="1501a-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="1501a-127">Uno sviluppatore può utilizzarli per informare la lettura dello schermo o qualsiasi altro client UIAutomation un'importante modifica apportata a un elemento dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1501a-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="1501a-128">La lettura dello schermo può quindi decidere come e quando per informare l'utente di questa modifica.</span><span class="sxs-lookup"><span data-stu-id="1501a-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="1501a-129">Per supportare le aree in tempo reale, le API seguenti sono state aggiunte a WPF:</span><span class="sxs-lookup"><span data-stu-id="1501a-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="1501a-130">Il <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> campi che identificano il **LiveSetting** proprietà e **LiveRegionChanged** evento.</span><span class="sxs-lookup"><span data-stu-id="1501a-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="1501a-131">Possono essere configurati per tramite XAML.</span><span class="sxs-lookup"><span data-stu-id="1501a-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="1501a-132">Il **AutomationProperties.LiveSetting** proprietà collegata, che indica la lettura dello schermo di importanza della modifica dell'interfaccia utente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1501a-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="1501a-133">Il <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> proprietà che identifica il **AutomationProperties.LiveSetting** proprietà associata.</span><span class="sxs-lookup"><span data-stu-id="1501a-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="1501a-134">Il <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> (metodo), che può essere sostituito per fornire un **LiveSetting** valore.</span><span class="sxs-lookup"><span data-stu-id="1501a-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="1501a-135">Il <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> i metodi, ottenere e impostare un **LiveSetting** valore.</span><span class="sxs-lookup"><span data-stu-id="1501a-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="1501a-136">Il <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumerazione, che definisce le seguenti possibili **LiveSetting** valori:</span><span class="sxs-lookup"><span data-stu-id="1501a-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="1501a-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1501a-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1501a-138">L'elemento non invia notifiche se è stato modificato il contenuto dell'area in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="1501a-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="1501a-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1501a-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1501a-140">L'elemento invia notifiche che non causano interruzioni se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="1501a-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="1501a-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1501a-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1501a-142">L'elemento invia notifiche con interruzioni se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="1501a-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="1501a-143">È possibile creare un LiveRegion impostando il **AutomationProperties.LiveSetting** proprietà sull'elemento di interesse, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1501a-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="1501a-144">Quando vengono modificati i dati nell'area in tempo reale ed è necessario informare lettura dello schermo, in modo esplicito un evento viene generato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1501a-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="1501a-145">**Contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="1501a-145">**High contrast**</span></span>

<span data-ttu-id="1501a-146">A partire da .NET Framework 4.7.1, sono stati apportati miglioramenti contrasto elevato per vari controlli WPF.</span><span class="sxs-lookup"><span data-stu-id="1501a-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="1501a-147">Sono ora visibili quando il <xref:System.Windows.SystemParameters.HighContrast%2A> tema è impostato.</span><span class="sxs-lookup"><span data-stu-id="1501a-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="1501a-148">tra cui:</span><span class="sxs-lookup"><span data-stu-id="1501a-148">These include:</span></span>

- <span data-ttu-id="1501a-149">Controllo <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="1501a-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="1501a-150">Lo stato attivo per il <xref:System.Windows.Controls.Expander> controllo è ora visibile.</span><span class="sxs-lookup"><span data-stu-id="1501a-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="1501a-151">Gli oggetti visivi della tastiera per <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, e <xref:System.Windows.Controls.RadioButton> anche i controlli sono visibili.</span><span class="sxs-lookup"><span data-stu-id="1501a-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="1501a-152">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1501a-152">For example:</span></span>

    <span data-ttu-id="1501a-153">Prima:</span><span class="sxs-lookup"><span data-stu-id="1501a-153">Before:</span></span> 
    
    ![Controllo Expander con lo stato attivo prima di miglioramenti di accessibilità](media/expander-before.png)

    <span data-ttu-id="1501a-155">Dopo:</span><span class="sxs-lookup"><span data-stu-id="1501a-155">After:</span></span> 

    ![Controllo Expander con lo stato attivo dopo i miglioramenti di accessibilità](media/expander-after.png)

- <span data-ttu-id="1501a-157"><xref:System.Windows.Controls.CheckBox>e <xref:System.Windows.Controls.RadioButton> controlli</span><span class="sxs-lookup"><span data-stu-id="1501a-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="1501a-158">Il testo di <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton> controlli è ora più semplice vedere quando selezionato in temi a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="1501a-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="1501a-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1501a-159">For example:</span></span>

    <span data-ttu-id="1501a-160">Prima:</span><span class="sxs-lookup"><span data-stu-id="1501a-160">Before:</span></span> 

    ![Pulsante di opzione Contrasto elevato con lo stato attivo prima di miglioramenti di accessibilità](media/radio-button-before.png)
    
    <span data-ttu-id="1501a-162">Dopo:</span><span class="sxs-lookup"><span data-stu-id="1501a-162">After:</span></span> 

    ![Pulsante di opzione Contrasto elevato con lo stato attivo dopo i miglioramenti di accessibilità](media/radio-button-after.png)

- <span data-ttu-id="1501a-164">Controllo <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="1501a-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="1501a-165">A partire da .NET Framework 4.7.1, il bordo di disattivato <xref:System.Windows.Controls.ComboBox> controllo è sullo stesso colore testo disabilitato.</span><span class="sxs-lookup"><span data-stu-id="1501a-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="1501a-166">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1501a-166">For example:</span></span>
    
    <span data-ttu-id="1501a-167">Prima:</span><span class="sxs-lookup"><span data-stu-id="1501a-167">Before:</span></span> 

     ![Casella combinata disabilitato bordo e il testo prima di miglioramenti di accessibilità](media/combo-disabled-before.png)

    <span data-ttu-id="1501a-169">Dopo:</span><span class="sxs-lookup"><span data-stu-id="1501a-169">After:</span></span>   

     ![Casella combinata disabilitato bordo e il testo dopo i miglioramenti di accessibilità](media/combo-disabled-after.png)

    <span data-ttu-id="1501a-171">Inoltre, i pulsanti con lo stato attivo e disabilitati utilizzano il colore del tema corretto.</span><span class="sxs-lookup"><span data-stu-id="1501a-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="1501a-172">Prima:</span><span class="sxs-lookup"><span data-stu-id="1501a-172">Before:</span></span>

    ![Colori del tema pulsante prima di miglioramenti di accessibilità](media/button-themes-before.png) 
    
    <span data-ttu-id="1501a-174">Dopo:</span><span class="sxs-lookup"><span data-stu-id="1501a-174">After:</span></span> 

    ![Colori del tema pulsante dopo i miglioramenti di accessibilità](media/button-themes-after.png) 

    <span data-ttu-id="1501a-176">Infine, in .NET Framework 4.7 e versioni precedenti, l'impostazione un <xref:System.Windows.Controls.ComboBox> stile del controllo `Toolbar.ComboBoxStyleKey` ha causato la freccia a discesa sia invisibile.</span><span class="sxs-lookup"><span data-stu-id="1501a-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="1501a-177">Questo problema è risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="1501a-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="1501a-178">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1501a-178">For example:</span></span>

    <span data-ttu-id="1501a-179">Prima:</span><span class="sxs-lookup"><span data-stu-id="1501a-179">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey prima di miglioramenti di accessibilità](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="1501a-181">Dopo:</span><span class="sxs-lookup"><span data-stu-id="1501a-181">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey dopo i miglioramenti di accessibilità](media/comboboxstylekey-after.png) 

- <span data-ttu-id="1501a-183">Controllo <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="1501a-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="1501a-184">A partire da .NET Framework 4.7.1, la freccia di ordinamento indicatore in <xref:System.Windows.Controls.DataGrid> controlla ora utilizza correzione i colori del tema.</span><span class="sxs-lookup"><span data-stu-id="1501a-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="1501a-185">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1501a-185">For example:</span></span>

    <span data-ttu-id="1501a-186">Prima:</span><span class="sxs-lookup"><span data-stu-id="1501a-186">Before:</span></span> 

    ![Freccia di ordinamento indicatore prima di miglioramenti di accessibilità](media/sort-indicator-before.png) 
    
    <span data-ttu-id="1501a-188">Dopo:</span><span class="sxs-lookup"><span data-stu-id="1501a-188">After:</span></span>   
 
    ![Freccia di ordinamento indicatore dopo i miglioramenti di accessibilità](media/sort-indicator-after.png) 
    
    <span data-ttu-id="1501a-190">Inoltre, in .NET Framework 4.7 e versioni precedenti, lo stile di collegamento predefinito modificato in un colore non corretto al passaggio del mouse in modalità a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="1501a-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="1501a-191">Questo viene risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="1501a-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="1501a-192">Analogamente, <xref:System.Windows.Controls.DataGrid> colonne casella di controllo vengono utilizzati i colori previsto per il feedback lo stato attivo della tastiera a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="1501a-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="1501a-193">Prima:</span><span class="sxs-lookup"><span data-stu-id="1501a-193">Before:</span></span> 

    ![Stile di collegamento predefinito DataGrid prima di miglioramenti di accessibilità](media/default-link-style-before.png) 
 
    <span data-ttu-id="1501a-195">Dopo:</span><span class="sxs-lookup"><span data-stu-id="1501a-195">After:</span></span>    
  
    ![Stile di collegamento predefinito DataGrid dopo i miglioramenti di accessibilità](media/default-link-style-after.png)  

<span data-ttu-id="1501a-197">Per ulteriori informazioni sui miglioramenti di accessibilità WPF in .NET Framework 4.7.1, vedere [miglioramenti di accessibilità in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="1501a-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="1501a-198">Miglioramenti di accessibilità di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1501a-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="1501a-199">In .NET Framework 4.7.1 Windows Form (Winform) include le modifiche di accesso nelle aree seguenti.</span><span class="sxs-lookup"><span data-stu-id="1501a-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="1501a-200">**Miglioramento della visualizzazione in modalità a contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="1501a-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="1501a-201">A partire da .NET Framework 4.7.1, vari controlli Windows Form offrono migliorate per il rendering in modalità di contrasto elevato disponibili nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1501a-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="1501a-202">I valori per alcuni colori di sistema di contrasto elevato è stato modificato da Windows 10 e Windows Form è basato su Windows 10 Win32 framework.</span><span class="sxs-lookup"><span data-stu-id="1501a-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="1501a-203">Per risultati ottimali, eseguire la versione più recente di Windows e consente di partecipare alle modifiche del sistema operativo più recente mediante l'aggiunta di che un file app. manifest in un'applicazione di test e un commento di Windows 10 supportate riga del sistema operativo in modo che esegua le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1501a-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="1501a-204">Alcuni esempi di modifiche di contrasto elevato:</span><span class="sxs-lookup"><span data-stu-id="1501a-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="1501a-205">Segni di spunta in <xref:System.Windows.Forms.MenuStrip> gli elementi sono più facili da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="1501a-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="1501a-206">Quando selezionato, disabilitato <xref:System.Windows.Forms.MenuStrip> gli elementi sono più facili da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="1501a-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="1501a-207">Testo in un determinato <xref:System.Windows.Forms.Button> controllare contrasta con il colore della selezione.</span><span class="sxs-lookup"><span data-stu-id="1501a-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="1501a-208">Testo disabilitato è più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="1501a-208">Disabled text is easier to read.</span></span> <span data-ttu-id="1501a-209">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1501a-209">For example:</span></span>

    <span data-ttu-id="1501a-210">Prima:</span><span class="sxs-lookup"><span data-stu-id="1501a-210">Before:</span></span>

    ![Testo disabilitato prima di miglioramenti di accessibilità](media/wf-disabled-before.png) 

    <span data-ttu-id="1501a-212">Dopo:</span><span class="sxs-lookup"><span data-stu-id="1501a-212">After:</span></span>

    ![Testo disabilitato dopo i miglioramenti di accessibilità](media/wf-disabled-after.png) 

- <span data-ttu-id="1501a-214">Miglioramenti di contrasto elevato nella finestra di dialogo di eccezione del Thread.</span><span class="sxs-lookup"><span data-stu-id="1501a-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="1501a-215">**Supporto migliorato di Assistente vocale**</span><span class="sxs-lookup"><span data-stu-id="1501a-215">**Improved Narrator support**</span></span>

<span data-ttu-id="1501a-216">Windows Form in .NET Framework 4.7.1 include i seguenti miglioramenti di accessibilità per l'Assistente vocale:</span><span class="sxs-lookup"><span data-stu-id="1501a-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="1501a-217">Il <xref:System.Windows.Forms.MonthCalendar> può accedere al controllo per l'Assistente vocale, nonché da altri strumenti di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1501a-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="1501a-218">Il <xref:System.Windows.Forms.CheckedListBox> controllo notifica dell'Assistente vocale quando lo stato di controllo di un elemento è stato modificato in modo che l'utente viene notificato che è stato modificato il valore di un elemento elenco.</span><span class="sxs-lookup"><span data-stu-id="1501a-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="1501a-219">Il <xref:System.Windows.Forms.DataGridViewCell> controllo segnala lo stato di sola lettura corretto per l'Assistente vocale.</span><span class="sxs-lookup"><span data-stu-id="1501a-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="1501a-220">Assistente vocale può ora leggere disabilitato <xref:System.Windows.Forms.ToolStripMenuItem> testo, mentre in precedenza ignorando le voci di menu disabilitata.</span><span class="sxs-lookup"><span data-stu-id="1501a-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="1501a-221">**Supporto avanzato per modelli di accessibilità UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="1501a-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="1501a-222">A partire da .NET Framework 4.7.1, gli sviluppatori di strumenti di accessibilità della tecnologia possono sfruttare modelli di accessibilità di API comuni e le proprietà per numerosi controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1501a-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="1501a-223">Questi miglioramenti di accessibilità includono:</span><span class="sxs-lookup"><span data-stu-id="1501a-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="1501a-224">Il <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ToolStripSplitButton> supportano ora il [patternExpandCollapse/](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="1501a-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="1501a-225">Il <xref:System.Windows.Forms.DataGridViewCheckBoxCell> supporta ora il [pattern toggle](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="1501a-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="1501a-226">Il <xref:System.Windows.Forms.ToolStripItem> controllo supporta il <xref:System.Windows.Automation.AutomationElement.Name> proprietà e [patternExpandCollapse/](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="1501a-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="1501a-227">Il <xref:System.Windows.Forms.NumericUpDown> e <xref:System.Windows.Forms.DomainUpDown> controlli supportano il <xref:System.Windows.Automation.automationElement.Name> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1501a-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.automationElement.Name> property.</span></span>

<span data-ttu-id="1501a-228">**Proprietà una migliore esperienza di browser**</span><span class="sxs-lookup"><span data-stu-id="1501a-228">**Improved property browser experience**</span></span>

<span data-ttu-id="1501a-229">A partire da .NET Framework 4.7.1, Windows Form include:</span><span class="sxs-lookup"><span data-stu-id="1501a-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="1501a-230">Una migliore navigazione tramite tastiera le varie finestre di selezione elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1501a-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="1501a-231">Riduzione dei punti di tabulazione non necessari.</span><span class="sxs-lookup"><span data-stu-id="1501a-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="1501a-232">Meglio reporting dei tipi di controllo.</span><span class="sxs-lookup"><span data-stu-id="1501a-232">Better reporting of control types.</span></span>
- <span data-ttu-id="1501a-233">Comportamento migliorato Assistente vocale.</span><span class="sxs-lookup"><span data-stu-id="1501a-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="1501a-234">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1501a-234">See Also</span></span>
[<span data-ttu-id="1501a-235">Novità di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1501a-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 