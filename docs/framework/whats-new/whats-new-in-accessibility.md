---
title: Nuove funzionalità di accessibilità in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 092b1cfc9350ea398eb18199f19a8eee7ea9f218
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675439"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="90807-102">Nuove funzionalità di accessibilità in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="90807-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="90807-103">Uno degli obiettivi di .NET Framework è rendere le applicazioni più accessibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="90807-103">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="90807-104">Le funzionalità di accessibilità consentono a un'applicazione di offrire un'esperienza appropriata per gli utenti di assistive technology.</span><span class="sxs-lookup"><span data-stu-id="90807-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="90807-105">A partire da .NET Framework 4.7.1, .NET Framework include numerosi miglioramenti per l'accessibilità che consentono agli sviluppatori di creare applicazioni accessibili.</span><span class="sxs-lookup"><span data-stu-id="90807-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

## <a name="accessibility-switches"></a><span data-ttu-id="90807-106">Opzioni di accessibilità</span><span class="sxs-lookup"><span data-stu-id="90807-106">Accessibility switches</span></span>

<span data-ttu-id="90807-107">È possibile configurare l'app per acconsentire esplicitamente alle funzionalità di accessibilità se l'app è destinata a .NET Framework 4.7 o a una versione precedente, ma viene eseguita in .NET Framework 4.7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="90807-107">You can configure your app to opt into accessibility features if it targets the .NET Framework 4.7 or an earlier version but is running on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="90807-108">È anche possibile configurare l'app per usare le funzionalità legacy, e rinunciare alle funzionalità di accessibilità, se l'app è destinata a .NET Framework 4.7.1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="90807-108">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="90807-109">Ogni versione di .NET Framework che include funzionalità di accessibilità ha un'opzione di accessibilità specifica per la versione, che è possibile aggiungere all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="90807-109">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="90807-110">Le opzioni supportate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="90807-110">The following are the supported switches:</span></span>

|<span data-ttu-id="90807-111">Versione</span><span class="sxs-lookup"><span data-stu-id="90807-111">Version</span></span>|<span data-ttu-id="90807-112">Opzione</span><span class="sxs-lookup"><span data-stu-id="90807-112">Switch</span></span>|
|---|---|
|<span data-ttu-id="90807-113">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="90807-113">.NET Framework 4.7.1</span></span>|<span data-ttu-id="90807-114">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="90807-114">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="90807-115">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="90807-115">.NET Framework 4.7.2</span></span>|<span data-ttu-id="90807-116">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="90807-116">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="90807-117">Sfruttare i vantaggi dei miglioramenti all'accessibilità</span><span class="sxs-lookup"><span data-stu-id="90807-117">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="90807-118">Le nuove funzionalità di accessibilità sono abilitate per impostazione predefinita per le applicazioni destinate a .NET Framework 4.7.1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="90807-118">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="90807-119">Oltre a ciò, le applicazioni destinate a una versione precedente di .NET Framework, ma eseguite in .NET Framework 4.7.1 o versioni successive, possono rifiutare esplicitamente comportamenti di accessibilità legacy (potendo così sfruttare i miglioramenti dell'accessibilità) aggiungendo opzioni all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione e impostandone il valore su `false`.</span><span class="sxs-lookup"><span data-stu-id="90807-119">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="90807-120">Di seguito viene illustrato come acconsentire esplicitamente ai miglioramenti apportati all'accessibilità introdotti in .NET Framework 4.7.1:</span><span class="sxs-lookup"><span data-stu-id="90807-120">The following shows how to opt in to accessibility enhancements introduced in the .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="90807-121">Se si sceglie di acconsentire esplicitamente alle funzionalità di accessibilità in una versione successiva di .NET Framework, è necessario anche acconsentire esplicitamente alle funzionalità di versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="90807-121">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="90807-122">La configurazione dell'app per sfruttare i miglioramenti all'accessibilità sia in .NET Framework 4.7.1 che 4.7.2 richiede l'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente:</span><span class="sxs-lookup"><span data-stu-id="90807-122">Configuring your app to take advantage of accessibility improvements in both the .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="90807-123">Ripristino del comportamento legacy</span><span class="sxs-lookup"><span data-stu-id="90807-123">Restoring legacy behavior</span></span>

<span data-ttu-id="90807-124">Le applicazioni destinate alle versioni di .NET Framework a partire dalla 4.7.1 possono disabilitare le funzionalità di accessibilità aggiungendo opzioni all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione e impostandone il valore su `true`.</span><span class="sxs-lookup"><span data-stu-id="90807-124">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="90807-125">Ad esempio, la configurazione seguente rifiuta esplicitamente le funzionalità di accessibilità introdotte in .NET Framework 4.7.2:</span><span class="sxs-lookup"><span data-stu-id="90807-125">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>  

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a><span data-ttu-id="90807-126">Nuove funzionalità di accessibilità in .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="90807-126">What's new in accessibility in the .NET Framework 4.7.2</span></span>

<span data-ttu-id="90807-127">.NET Framework 4.7.2 include nuove funzionalità di accessibilità nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="90807-127">The .NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="90807-128">Windows Form</span><span class="sxs-lookup"><span data-stu-id="90807-128">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="90807-129">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="90807-129">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>
### <a name="windows-forms"></a><span data-ttu-id="90807-130">Windows Form</span><span class="sxs-lookup"><span data-stu-id="90807-130">Windows Forms</span></span>

<span data-ttu-id="90807-131">**Colori definiti dal sistema operativo nei temi a contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="90807-131">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="90807-132">A partire da .NET Framework 4.7.2, Windows Forms usa colori definiti dal sistema operativo dei temi di contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="90807-132">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="90807-133">Ciò influisce sui controlli seguenti:</span><span class="sxs-lookup"><span data-stu-id="90807-133">This affects the following controls:</span></span>

- <span data-ttu-id="90807-134">La freccia a discesa del controllo <xref:System.Windows.Forms.ToolStripDropDownButton>.</span><span class="sxs-lookup"><span data-stu-id="90807-134">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="90807-135">I controlli <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con <xref:System.Windows.Forms.ButtonBase.FlatStyle> impostato su <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> o <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90807-135">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="90807-136">In precedenza, i colori dello sfondo e del testo selezionato non erano in contrasto e risultavano di difficile lettura.</span><span class="sxs-lookup"><span data-stu-id="90807-136">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="90807-137">I controlli contenuti in un oggetto <xref:System.Windows.Forms.GroupBox> con la proprietà relativa <xref:System.Windows.Forms.Control.Enabled> impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="90807-137">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>
 
- <span data-ttu-id="90807-138">I controlli <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> e <xref:System.Windows.Forms.ToolStripDropDownButton> che hanno un maggiore rapporto del contrasto di luminosità nella modalità a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="90807-138">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="90807-139">La proprietà <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> di <xref:System.Windows.Forms.DataGridViewLinkCell>.</span><span class="sxs-lookup"><span data-stu-id="90807-139">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="90807-140">**Miglioramenti di Assistente vocale**</span><span class="sxs-lookup"><span data-stu-id="90807-140">**Narrator improvements**</span></span>

<span data-ttu-id="90807-141">A partire da .NET Framework 4.7.2, il supporto di Assistente vocale è stato migliorato come segue:</span><span class="sxs-lookup"><span data-stu-id="90807-141">Starting with the .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="90807-142">Annuncia il valore della proprietà <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> mentre annuncia il testo di una classe <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="90807-142">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span> 

- <span data-ttu-id="90807-143">Indica quando una classe <xref:System.Windows.Forms.ToolStripMenuItem> ha la proprietà <xref:System.Windows.Forms.Control.Enabled> impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="90807-143">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="90807-144">Offre un feedback sullo stato di una casella di controllo quando la proprietà <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="90807-144">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="90807-145">L'ordine di attivazione nella modalità di analisi dell'Assistente vocale rispetta l'ordine degli oggetti visivi dei controlli nella finestra di dialogo di download ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="90807-145">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="90807-146">**Miglioramenti apportati a DataGridView**</span><span class="sxs-lookup"><span data-stu-id="90807-146">**DataGridView improvements**</span></span>

<span data-ttu-id="90807-147">A partire da .NET Framework 4.7.2, il controllo <xref:System.Windows.Forms.DataGridView> ha introdotto i miglioramenti di accessibilità seguenti:</span><span class="sxs-lookup"><span data-stu-id="90807-147">Starting with the .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="90807-148">Le righe possono essere ordinate usando la tastiera.</span><span class="sxs-lookup"><span data-stu-id="90807-148">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="90807-149">È possibile usare F3 per ordinare in base alla colonna corrente.</span><span class="sxs-lookup"><span data-stu-id="90807-149">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="90807-150">Quando la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, l'intestazione di colonna cambia colore per indicare la colonna corrente man mano che l'utente si sposta tra le celle nella riga corrente tramite tabulazione.</span><span class="sxs-lookup"><span data-stu-id="90807-150">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="90807-151">La proprietà <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> di un oggetto <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> restituisce il controllo padre corretto.</span><span class="sxs-lookup"><span data-stu-id="90807-151">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="90807-152">**Segnali visivi migliorati**</span><span class="sxs-lookup"><span data-stu-id="90807-152">**Improved visual cues**</span></span>

- <span data-ttu-id="90807-153">I controlli <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con proprietà <xref:System.Windows.Forms.ButtonBase.Text> vuota visualizzano un indicatore di stato attivo quando ricevono lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="90807-153">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="90807-154">**Supporto migliorato per PropertyGrid**</span><span class="sxs-lookup"><span data-stu-id="90807-154">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="90807-155">Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> ora restituiscono `true` per la proprietà <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> solo quando è abilitato un elemento PropertyGrid.</span><span class="sxs-lookup"><span data-stu-id="90807-155">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="90807-156">Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> restituiscono `false` per la proprietà <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> solo quando un elemento PropertyGrid può essere modificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="90807-156">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="90807-157">**Navigazione tramite tastiera migliorata**</span><span class="sxs-lookup"><span data-stu-id="90807-157">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="90807-158">Il controllo <xref:System.Windows.Forms.ToolStripButton> consente lo stato attivo quando è contenuto all'interno di una classe <xref:System.Windows.Forms.ToolStripPanel> con la proprietà <xref:System.Windows.Forms.ToolStripPanel.TabStop> impostata su `true`</span><span class="sxs-lookup"><span data-stu-id="90807-158">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>
### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="90807-159">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="90807-159">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="90807-160">**Modifiche ai controlli CheckBox e RadioButton**</span><span class="sxs-lookup"><span data-stu-id="90807-160">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="90807-161">In .NET Framework 4.7.1 e versioni precedenti i controlli <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> e <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> di WPF contengono oggetti visivi dello stato attivo incoerenti e non corretti nei temi classico e a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="90807-161">In the .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="90807-162">Questi problemi si verificano se i controlli non hanno impostato un contenuto.</span><span class="sxs-lookup"><span data-stu-id="90807-162">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="90807-163">La transizione tra i temi può risultare quindi confusa e diventa difficile visualizzare l'oggetto visivo con stato attivo.</span><span class="sxs-lookup"><span data-stu-id="90807-163">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="90807-164">In .NET Framework 4.7.2 questi oggetti visivi sono più coerenti tra i temi e possono essere visualizzati più facilmente nei temi classico e a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="90807-164">In the .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="90807-165">**Controlli WinForms ospitati in un'applicazione WPF**</span><span class="sxs-lookup"><span data-stu-id="90807-165">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="90807-166">Nel caso di un controllo WinForms ospitato in un'applicazione WPF in .NET Framework 4.7.1 e versioni precedenti, gli utenti non potevano uscire dal livello WinForms se il primo o l'ultimo controllo nel livello era il controllo <xref:System.Windows.Forms.Integration.ElementHost> di WPF.</span><span class="sxs-lookup"><span data-stu-id="90807-166">For WinForms control hosted in a WPF application in the .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="90807-167">In .NET Framework 4.7.2 gli utenti possono uscire dal livello di WinForms.</span><span class="sxs-lookup"><span data-stu-id="90807-167">In the .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="90807-168">Tuttavia, le applicazioni automatiche che si basano sullo stato attivo che non esce mai dal livello di WinForms potrebbero non funzionare più come previsto.</span><span class="sxs-lookup"><span data-stu-id="90807-168">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="90807-169">Nuove funzionalità di accessibilità in .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="90807-169">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="90807-170">.NET Framework 4.7.1 include nuove funzionalità di accessibilità nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="90807-170">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="90807-171">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="90807-171">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="90807-172">Windows Form</span><span class="sxs-lookup"><span data-stu-id="90807-172">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="90807-173">Controlli Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="90807-173">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="90807-174">Strumenti .NET SDK</span><span class="sxs-lookup"><span data-stu-id="90807-174">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="90807-175">Progettazione flussi di lavoro di Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="90807-175">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>
### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="90807-176">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="90807-176">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="90807-177">**Miglioramenti per le utilità per la lettura dello schermo**</span><span class="sxs-lookup"><span data-stu-id="90807-177">**Screen reader improvements**</span></span>

<span data-ttu-id="90807-178">Se sono abilitati i miglioramenti per l'accessibilità, .NET Framework 4.7.1 include i miglioramenti seguenti che riguardano le utilità per la lettura dello schermo:</span><span class="sxs-lookup"><span data-stu-id="90807-178">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="90807-179">In .NET Framework 4.7 e versioni precedenti, i controlli <xref:System.Windows.Controls.Expander> vengono annunciati come pulsanti dalle utilità per la lettura dello schermo.</span><span class="sxs-lookup"><span data-stu-id="90807-179">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="90807-180">A partire da .NET Framework 4.7.1, sono annunciati correttamente come gruppi espandibili/comprimibili.</span><span class="sxs-lookup"><span data-stu-id="90807-180">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="90807-181">In .NET Framework 4.7 e versioni precedenti, i controlli <xref:System.Windows.Controls.DataGridCell> vengono annunciati come "personalizzati".</span><span class="sxs-lookup"><span data-stu-id="90807-181">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="90807-182">A partire da .NET Framework 4.7.1, sono annunciati correttamente come cella di griglia dati (localizzati).</span><span class="sxs-lookup"><span data-stu-id="90807-182">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="90807-183">A partire da .NET Framework 4.7.1, le utilità per la lettura dello schermo annunciano il nome di un controllo <xref:System.Windows.Controls.ComboBox> modificabile.</span><span class="sxs-lookup"><span data-stu-id="90807-183">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="90807-184">In .NET Framework 4.7 e versioni precedenti, i controlli <xref:System.Windows.Controls.PasswordBox> vengono annunciati come "Nessun elemento visualizzato" o il comportamento è in altro modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="90807-184">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="90807-185">Questo problema è stato risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="90807-185">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>

<span data-ttu-id="90807-186">**Supporto di aree dinamiche UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="90807-186">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="90807-187">Le utilità per la lettura dello schermo, come Assistente vocale, consentono di leggere il contenuto dell'interfaccia utente di un'applicazione, in genere annunciando tramite sintesi vocale il contenuto dell'interfaccia utente con lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="90807-187">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="90807-188">Tuttavia, se un elemento dell'interfaccia utente viene modificato e non ha lo stato attivo, l'utente potrebbe non ricevere notifica e perdere informazioni importanti.</span><span class="sxs-lookup"><span data-stu-id="90807-188">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="90807-189">Le aree dinamiche sono progettate per risolvere questo problema.</span><span class="sxs-lookup"><span data-stu-id="90807-189">Live regions aim at solving this problem.</span></span> <span data-ttu-id="90807-190">Uno sviluppatore può usarle per informare l'utilità per la lettura dello schermo o qualsiasi altro client UIAutomation di un'importante modifica apportata a un elemento dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="90807-190">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="90807-191">L'utilità per la lettura dello schermo può quindi decidere come e quando informare l'utente di questa modifica.</span><span class="sxs-lookup"><span data-stu-id="90807-191">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="90807-192">Per supportare le aree dinamiche sono state aggiunte le API seguenti a WPF:</span><span class="sxs-lookup"><span data-stu-id="90807-192">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="90807-193">I campi <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> che identificano la proprietà **LiveSetting** e l'evento **LiveRegionChanged**.</span><span class="sxs-lookup"><span data-stu-id="90807-193">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="90807-194">Questi campi possono essere impostati tramite XAML.</span><span class="sxs-lookup"><span data-stu-id="90807-194">They can be set by using XAML.</span></span>

- <span data-ttu-id="90807-195">La proprietà associata **AutomationProperties.LiveSetting** che segnala all'utilità per la lettura dello schermo l'importanza della modifica dell'interfaccia utente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="90807-195">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="90807-196">La proprietà <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, che identifica la proprietà associata **AutomationProperties.LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="90807-196">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="90807-197">Il metodo <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, di cui è possibile eseguire l'override per specificare un valore **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="90807-197">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="90807-198">I metodi <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, che consentono di ottenere e impostare un valore **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="90807-198">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="90807-199">L'enumerazione <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, che definisce le i valori **LiveSetting** possibili seguenti:</span><span class="sxs-lookup"><span data-stu-id="90807-199">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="90807-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90807-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="90807-201">L'elemento non invia notifiche se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="90807-201">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="90807-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90807-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="90807-203">L'elemento invia notifiche che non causano interruzioni se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="90807-203">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="90807-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90807-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="90807-205">L'elemento invia notifiche con interruzioni se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="90807-205">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="90807-206">È possibile creare un'area dinamica impostando la proprietà **AutomationProperties.LiveSetting** sull'elemento di interesse, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="90807-206">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="90807-207">Quando vengono modificati i dati nell'area dinamica ed è necessario informarne un'utilità per la lettura dello schermo, deve essere generato un evento in modo esplicito, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="90807-207">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="90807-208">**Contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="90807-208">**High contrast**</span></span>

<span data-ttu-id="90807-209">A partire da .NET Framework 4.7.1, sono stati apportati miglioramenti relativi al contrasto elevato per vari controlli WPF,</span><span class="sxs-lookup"><span data-stu-id="90807-209">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="90807-210">che sono ora visibili quando viene impostato il tema <xref:System.Windows.SystemParameters.HighContrast%2A>.</span><span class="sxs-lookup"><span data-stu-id="90807-210">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="90807-211">Sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="90807-211">These include:</span></span>

- <span data-ttu-id="90807-212">Controllo <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="90807-212"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="90807-213">L'oggetto visivo per lo stato attivo per il controllo <xref:System.Windows.Controls.Expander> è ora visibile.</span><span class="sxs-lookup"><span data-stu-id="90807-213">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="90807-214">Anche gli oggetti visivi della tastiera per i controlli <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.RadioButton> sono visibili.</span><span class="sxs-lookup"><span data-stu-id="90807-214">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="90807-215">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90807-215">For example:</span></span>

    <span data-ttu-id="90807-216">Prima:</span><span class="sxs-lookup"><span data-stu-id="90807-216">Before:</span></span> 
    
    ![Controllo Expander con lo stato attivo prima dei miglioramenti per l'accessibilità](media/expander-before.png)

    <span data-ttu-id="90807-218">Dopo:</span><span class="sxs-lookup"><span data-stu-id="90807-218">After:</span></span> 

    ![Controllo Expander con lo stato attivo dopo i miglioramenti per l'accessibilità](media/expander-after.png)

- <span data-ttu-id="90807-220">Controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton></span><span class="sxs-lookup"><span data-stu-id="90807-220"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="90807-221">Il testo nei controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton> è ora più semplice da vedere quando viene selezionato nei temi a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="90807-221">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="90807-222">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90807-222">For example:</span></span>

    <span data-ttu-id="90807-223">Prima:</span><span class="sxs-lookup"><span data-stu-id="90807-223">Before:</span></span> 

    ![Pulsante di opzione con contrasto elevato con lo stato attivo prima dei miglioramenti per l'accessibilità](media/radio-button-before.png)
    
    <span data-ttu-id="90807-225">Dopo:</span><span class="sxs-lookup"><span data-stu-id="90807-225">After:</span></span> 

    ![Pulsante di opzione con contrasto elevato con lo stato attivo dopo i miglioramenti per l'accessibilità](media/radio-button-after.png)

- <span data-ttu-id="90807-227">Controllo <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="90807-227"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="90807-228">A partire da .NET Framework 4.7.1, il bordo di un controllo <xref:System.Windows.Controls.ComboBox> disabilitato ha lo stesso colore del testo disabilitato.</span><span class="sxs-lookup"><span data-stu-id="90807-228">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="90807-229">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90807-229">For example:</span></span>
    
    <span data-ttu-id="90807-230">Prima:</span><span class="sxs-lookup"><span data-stu-id="90807-230">Before:</span></span> 

     ![Bordo e testo disabilitati del controllo ComboBox prima dei miglioramenti per l'accessibilità](media/combo-disabled-before.png)

    <span data-ttu-id="90807-232">Dopo:</span><span class="sxs-lookup"><span data-stu-id="90807-232">After:</span></span>   

     ![Bordo e testo disabilitati del controllo ComboBox dopo i miglioramenti per l'accessibilità](media/combo-disabled-after.png)

    <span data-ttu-id="90807-234">Inoltre, i pulsanti con lo stato attivo e disabilitati usano il colore del tema corretto.</span><span class="sxs-lookup"><span data-stu-id="90807-234">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="90807-235">Prima:</span><span class="sxs-lookup"><span data-stu-id="90807-235">Before:</span></span>

    ![Colori del tema dei pulsanti prima dei miglioramenti per l'accessibilità](media/button-themes-before.png) 
    
    <span data-ttu-id="90807-237">Dopo:</span><span class="sxs-lookup"><span data-stu-id="90807-237">After:</span></span> 

    ![Colori del tema dei pulsanti dopo i miglioramenti per l'accessibilità](media/button-themes-after.png) 

    <span data-ttu-id="90807-239">Infine, in .NET Framework 4.7 e versioni precedenti, l'impostazione dello stile di un controllo <xref:System.Windows.Controls.ComboBox> su `Toolbar.ComboBoxStyleKey` rende invisibile la freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="90807-239">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="90807-240">Questo problema è stato risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="90807-240">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="90807-241">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90807-241">For example:</span></span>

    <span data-ttu-id="90807-242">Prima:</span><span class="sxs-lookup"><span data-stu-id="90807-242">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey prima dei miglioramenti per l'accessibilità](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="90807-244">Dopo:</span><span class="sxs-lookup"><span data-stu-id="90807-244">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey dopo i miglioramenti per l'accessibilità](media/comboboxstylekey-after.png) 

- <span data-ttu-id="90807-246">Controllo <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="90807-246"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="90807-247">A partire da .NET Framework 4.7.1, la freccia dell'indicatore di ordinamento nei controlli <xref:System.Windows.Controls.DataGrid> usa ora i colori del tema corretti.</span><span class="sxs-lookup"><span data-stu-id="90807-247">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="90807-248">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90807-248">For example:</span></span>

    <span data-ttu-id="90807-249">Prima:</span><span class="sxs-lookup"><span data-stu-id="90807-249">Before:</span></span> 

    ![Freccia dell'indicatore di ordinamento prima dei miglioramenti per l'accessibilità](media/sort-indicator-before.png) 
    
    <span data-ttu-id="90807-251">Dopo:</span><span class="sxs-lookup"><span data-stu-id="90807-251">After:</span></span>   
 
    ![Freccia dell'indicatore di ordinamento dopo i miglioramenti per l'accessibilità](media/sort-indicator-after.png) 
    
    <span data-ttu-id="90807-253">Inoltre, in .NET Framework 4.7 e versioni precedenti, per lo stile di collegamento predefinito viene usato un colore non corretto al passaggio del mouse in modalità a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="90807-253">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="90807-254">Questo problema è stato risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="90807-254">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="90807-255">Analogamente, le colonne della casella di controllo per i controlli <xref:System.Windows.Controls.DataGrid> usano i colori previsti per il riscontro dello stato attivo della tastiera a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="90807-255">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="90807-256">Prima:</span><span class="sxs-lookup"><span data-stu-id="90807-256">Before:</span></span> 

    ![Stile di collegamento predefinito DataGrid prima dei miglioramenti per l'accessibilità](media/default-link-style-before.png) 
 
    <span data-ttu-id="90807-258">Dopo:</span><span class="sxs-lookup"><span data-stu-id="90807-258">After:</span></span>    
  
    ![Stile di collegamento predefinito DataGrid dopo i miglioramenti per l'accessibilità](media/default-link-style-after.png)  

<span data-ttu-id="90807-260">Per altre informazioni sui miglioramenti per l'accessibilità di WPF in .NET Framework 4.7.1, vedere [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf) (Miglioramenti per l'accessibilità in WPF).</span><span class="sxs-lookup"><span data-stu-id="90807-260">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>
### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="90807-261">Miglioramenti per l'accessibilità di Windows Form</span><span class="sxs-lookup"><span data-stu-id="90807-261">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="90807-262">In .NET Framework 4.7.1 Windows Form (WinForms) include modifiche per l'accessibilità nelle aree seguenti.</span><span class="sxs-lookup"><span data-stu-id="90807-262">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="90807-263">**Miglioramento della visualizzazione in modalità a contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="90807-263">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="90807-264">A partire da .NET Framework 4.7.1, vari controlli WinForms offrono un rendering migliorato nelle modalità a contrasto elevato disponibili nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="90807-264">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="90807-265">Windows 10 ha cambiato i valori di alcuni colori di sistema a contrasto elevato e Windows Form si basa sul framework Win32 di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="90807-265">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="90807-266">Per risultati ottimali, usare la versione più recente di Windows e accettare le modifiche del sistema operativo più recenti aggiungendo un file app.manifest in un'applicazione di test e rimuovere il commento dalla riga del sistema operativo supportato Windows 10, in modo che abbia l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="90807-266">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="90807-267">Alcuni esempi di modifiche per il contrasto elevato includono:</span><span class="sxs-lookup"><span data-stu-id="90807-267">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="90807-268">I segni di spunta negli elementi <xref:System.Windows.Forms.MenuStrip> sono più facili da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="90807-268">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="90807-269">Gli elementi <xref:System.Windows.Forms.MenuStrip> disabilitati sono più facili da visualizzare quando sono selezionati.</span><span class="sxs-lookup"><span data-stu-id="90807-269">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="90807-270">Il testo in un controllo <xref:System.Windows.Forms.Button> selezionato è contrastato rispetto al colore della selezione.</span><span class="sxs-lookup"><span data-stu-id="90807-270">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="90807-271">Il testo disabilitato è più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="90807-271">Disabled text is easier to read.</span></span> <span data-ttu-id="90807-272">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90807-272">For example:</span></span>

    <span data-ttu-id="90807-273">Prima:</span><span class="sxs-lookup"><span data-stu-id="90807-273">Before:</span></span>

    ![Testo disabilitato prima dei miglioramenti per l'accessibilità](media/wf-disabled-before.png) 

    <span data-ttu-id="90807-275">Dopo:</span><span class="sxs-lookup"><span data-stu-id="90807-275">After:</span></span>

    ![Testo disabilitato dopo i miglioramenti per l'accessibilità](media/wf-disabled-after.png) 

- <span data-ttu-id="90807-277">Miglioramenti per il contrasto elevato nella finestra di dialogo di eccezione del thread.</span><span class="sxs-lookup"><span data-stu-id="90807-277">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="90807-278">**Supporto migliorato di Assistente vocale**</span><span class="sxs-lookup"><span data-stu-id="90807-278">**Improved Narrator support**</span></span>

<span data-ttu-id="90807-279">Windows Form in .NET Framework 4.7.1 include i seguenti miglioramenti per l'accessibilità per l'Assistente vocale:</span><span class="sxs-lookup"><span data-stu-id="90807-279">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="90807-280">Il controllo <xref:System.Windows.Forms.MonthCalendar> è accessibile per l'Assistente vocale, così come da altri strumenti di automazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="90807-280">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="90807-281">Il controllo <xref:System.Windows.Forms.CheckedListBox> segnala all'Assistente vocale lo stato di selezione di un elemento, in modo che l'utente riceva notifica della modifica del valore di un elemento di elenco.</span><span class="sxs-lookup"><span data-stu-id="90807-281">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="90807-282">Il controllo <xref:System.Windows.Forms.DataGridViewCell> segnala lo stato di sola lettura corretto all'Assistente vocale.</span><span class="sxs-lookup"><span data-stu-id="90807-282">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="90807-283">Assistente vocale può ora leggere il testo <xref:System.Windows.Forms.ToolStripMenuItem> disabilitato, mentre in precedenza ignorava le voci di menu disabilitate.</span><span class="sxs-lookup"><span data-stu-id="90807-283">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="90807-284">**Supporto avanzato per i modelli di accessibilità UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="90807-284">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="90807-285">A partire da .NET Framework 4.7.1, gli sviluppatori di strumenti di tecnologia per l'accessibilità possono sfruttare i modelli e le proprietà di accessibilità delle API comuni per numerosi controlli WinForms.</span><span class="sxs-lookup"><span data-stu-id="90807-285">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="90807-286">Questi miglioramenti per l'accessibilità includono:</span><span class="sxs-lookup"><span data-stu-id="90807-286">These accessibility improvements include:</span></span>

- <span data-ttu-id="90807-287"><xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ToolStripSplitButton> ora supportano il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="90807-287">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="90807-288"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> supporta ora il [modello di attivazione/disattivazione](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="90807-288">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="90807-289">Il controllo <xref:System.Windows.Forms.ToolStripItem> supporta la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> e il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="90807-289">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="90807-290">I controlli <xref:System.Windows.Forms.NumericUpDown> e <xref:System.Windows.Forms.DomainUpDown> supportano la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.</span><span class="sxs-lookup"><span data-stu-id="90807-290">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="90807-291">**Esperienza migliorata per il visualizzatore proprietà**</span><span class="sxs-lookup"><span data-stu-id="90807-291">**Improved property browser experience**</span></span>

<span data-ttu-id="90807-292">A partire da .NET Framework 4.7.1, Windows Form include:</span><span class="sxs-lookup"><span data-stu-id="90807-292">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="90807-293">Migliori spostamenti tramite tastiera tra le varie finestre di selezione a discesa.</span><span class="sxs-lookup"><span data-stu-id="90807-293">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="90807-294">Riduzione dei punti di tabulazione non necessari.</span><span class="sxs-lookup"><span data-stu-id="90807-294">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="90807-295">Segnalazione migliore dei tipi di controllo.</span><span class="sxs-lookup"><span data-stu-id="90807-295">Better reporting of control types.</span></span>
- <span data-ttu-id="90807-296">Comportamento migliorato dell'Assistente vocale.</span><span class="sxs-lookup"><span data-stu-id="90807-296">Improved narrator behavior.</span></span>
 
<a name="aspnet471"></a>
### <a name="aspnet-web-controls"></a><span data-ttu-id="90807-297">Controlli Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="90807-297">ASP.NET web controls</span></span>

<span data-ttu-id="90807-298">A partire da .NET Framework 4.7.1 e Visual Studio 2017 15.3, in ASP.NET è stato migliorato il funzionamento dei controlli Web ASP.NET con tecnologia di accessibilità in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="90807-298">Starting with the .NET Framework 4.7.1 and Visual Studio 2017 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="90807-299">Le modifiche includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="90807-299">Changes include the following:</span></span>

- <span data-ttu-id="90807-300">Modifiche per implementare criteri di accessibilità dell'interfaccia utente mancanti nei controlli, come la finestra di dialogo **Aggiungi campo** nella procedura guidata **Visualizzazione dettagli** o la finestra di dialogo **Configura ListView** nella procedura guidata **ListView**.</span><span class="sxs-lookup"><span data-stu-id="90807-300">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="90807-301">Modifiche per migliorare la visualizzazione nella modalità a contrasto elevato, ad esempio l'**Editor campi del pager di dati**.</span><span class="sxs-lookup"><span data-stu-id="90807-301">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="90807-302">Modifiche per migliorare la navigazione tramite tastiera per controlli, come la finestra di dialogo **Campi** nella procedura guidata **Modifica campi del pager** del controllo DataPager, la finestra di dialogo **Configura ObjectContext** o la finestra di dialogo **Configura selezione dati** della procedura guidata **Configura origine dati**.</span><span class="sxs-lookup"><span data-stu-id="90807-302">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>
### <a name="net-sdk-tools"></a><span data-ttu-id="90807-303">Strumenti .NET SDK</span><span class="sxs-lookup"><span data-stu-id="90807-303">.NET SDK Tools</span></span>

<span data-ttu-id="90807-304">Lo [strumento Editor di configurazione (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) e lo [strumento Visualizzatore di tracce (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) sono stati migliorati correggendo vari problemi di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="90807-304">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="90807-305">Molti erano problemi di lieve entità, come ad esempio un nome non definito o alcuni criteri dell'automazione interfaccia utente non implementati correttamente.</span><span class="sxs-lookup"><span data-stu-id="90807-305">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="90807-306">È possibile che molti utenti non si siano accorti di questi valori non corretti. I clienti che usano le assistive technology, ad esempio le utilità per la lettura dello schermo, troveranno invece questi strumenti SDK più accessibili.</span><span class="sxs-lookup"><span data-stu-id="90807-306">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> 

<span data-ttu-id="90807-307">Tali miglioramenti modificano alcuni comportamenti precedenti, ad esempio l'ordine di attivazione della tastiera.</span><span class="sxs-lookup"><span data-stu-id="90807-307">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>
### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="90807-308">Progettazione flussi di lavoro di Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="90807-308">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="90807-309">Le modifiche all'accessibilità in Progettazione flussi di lavoro includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="90807-309">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="90807-310">L'ordine di tabulazione viene modificato da sinistra a destra e dall'alto verso il basso in alcuni controlli:</span><span class="sxs-lookup"><span data-stu-id="90807-310">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="90807-311">La finestra di inizializzazione della correlazione in cui impostare i dati di correlazione per l'attività <xref:System.ServiceModel.Activities.InitializeCorrelation>.</span><span class="sxs-lookup"><span data-stu-id="90807-311">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="90807-312">La finestra di definizione del contenuto per le attività <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>.</span><span class="sxs-lookup"><span data-stu-id="90807-312">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="90807-313">Altre funzioni sono disponibili tramite tastiera:</span><span class="sxs-lookup"><span data-stu-id="90807-313">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="90807-314">Quando vengono modificate le proprietà di un'attività, i gruppi delle proprietà possono essere compressi tramite tastiera la prima volta che hanno lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="90807-314">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="90807-315">Le icone di avviso sono accessibili dalla tastiera.</span><span class="sxs-lookup"><span data-stu-id="90807-315">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="90807-316">Il pulsante **Altre proprietà** nella finestra **Proprietà** è accessibile dalla tastiera.</span><span class="sxs-lookup"><span data-stu-id="90807-316">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="90807-317">Tramite tastiera gli utenti possono accedere agli elementi dell'intestazione nei riquadri **Argomenti** e **Variabili** in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="90807-317">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="90807-318">Maggiore visibilità degli elementi con stato attivo, ad esempio quando:</span><span class="sxs-lookup"><span data-stu-id="90807-318">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="90807-319">Aggiunta di righe alle griglie di dati usate in Progettazione flussi di lavoro e in ActivityDesigner.</span><span class="sxs-lookup"><span data-stu-id="90807-319">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="90807-320">Tabulazione all'interno dei campi nelle attività <xref:System.ServiceModel.Activities.ReceiveReply> e <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="90807-320">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="90807-321">Impostazione di valori predefiniti per variabili o argomenti</span><span class="sxs-lookup"><span data-stu-id="90807-321">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="90807-322">Le utilità per la lettura dello schermo ora possono riconoscere correttamente:</span><span class="sxs-lookup"><span data-stu-id="90807-322">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="90807-323">Set di punti di interruzione in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="90807-323">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="90807-324">Attività <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> e <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="90807-324">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="90807-325">Contenuto dell'attività <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="90807-325">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="90807-326">Tipo di destinazione per l'attività <xref:System.Activities.Statements.InvokeMethod>.</span><span class="sxs-lookup"><span data-stu-id="90807-326">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="90807-327">Casella combinata Eccezione e sezione Finally nell'attività <xref:System.Activities.Statements.TryCatch>.</span><span class="sxs-lookup"><span data-stu-id="90807-327">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="90807-328">Casella combinata Tipo di messaggio, barra di divisione nella finestra Aggiungi inizializzatori di correlazione, finestra Content Definition (Definizione contenuto) e finestra Definizione di CorrelatesOn nelle attività di messaggistica (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>).</span><span class="sxs-lookup"><span data-stu-id="90807-328">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="90807-329">Transizioni della macchina a uno stato e destinazioni delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="90807-329">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="90807-330">Annotazioni e connettori nelle attività <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="90807-330">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="90807-331">Menu di scelta rapida per le attività.</span><span class="sxs-lookup"><span data-stu-id="90807-331">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="90807-332">Editor di valori di proprietà, pulsante Cancella ricerca, pulsanti di ordinamento Per categoria e In ordine alfabetico e finestra di dialogo Editor espressioni nella griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="90807-332">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="90807-333">Percentuale di zoom in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="90807-333">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="90807-334">Separatore nelle attività <xref:System.Activities.Statements.Parallel> e <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="90807-334">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="90807-335">Attività <xref:System.Activities.Statements.InvokeDelegate>.</span><span class="sxs-lookup"><span data-stu-id="90807-335">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="90807-336">Finestra Seleziona tipi per le attività di dizionario (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` e così via).</span><span class="sxs-lookup"><span data-stu-id="90807-336">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="90807-337">Finestra Cerca e seleziona un tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="90807-337">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="90807-338">Navigazioni in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="90807-338">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="90807-339">Gli utenti che usano i temi a contrasto elevato noteranno molti miglioramenti nella visibilità di Progettazione flussi di lavoro e nei relativi controlli, ad esempio rapporti di contrasto più definiti tra gli elementi e caselle di selezione più evidenti per gli elementi con lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="90807-339">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="90807-340">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90807-340">See also</span></span>

- [<span data-ttu-id="90807-341">Novità di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="90807-341">What's new in the .NET Framework</span></span>](whats-new.md)

