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
ms.openlocfilehash: 2bdb1bf5d7e32c2e05eb779eed16c311cbd3eae7
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212508"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Nuove funzionalità di accessibilità in .NET Framework

Uno degli obiettivi di .NET Framework è rendere le applicazioni più accessibili per gli utenti. Le funzionalità di accessibilità consentono a un'applicazione di offrire un'esperienza appropriata per gli utenti di assistive technology. A partire da .NET Framework 4.7.1, .NET Framework include numerosi miglioramenti per l'accessibilità che consentono agli sviluppatori di creare applicazioni accessibili.

## <a name="accessibility-switches"></a>Opzioni di accessibilità

È possibile configurare l'app per acconsentire esplicitamente alle funzionalità di accessibilità se l'app è destinata a .NET Framework 4.7 o a una versione precedente, ma viene eseguita in .NET Framework 4.7.1 o versione successiva. È anche possibile configurare l'app per usare le funzionalità legacy, e rinunciare alle funzionalità di accessibilità, se l'app è destinata a .NET Framework 4.7.1 o versioni successive. Ogni versione di .NET Framework che include funzionalità di accessibilità ha un'opzione di accessibilità specifica per la versione, che è possibile aggiungere all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione. Le opzioni supportate sono le seguenti:

|Versione|Opzione|
|---|---|
|.NET Framework 4.7.1|"Switch.UseLegacyAccessibilityFeatures"|
|.NET Framework 4.7.2|"Switch.UseLegacyAccessibilityFeatures.2"|

### <a name="taking-advantage-of-accessibility-enhancements"></a>Sfruttare i vantaggi dei miglioramenti all'accessibilità

Le nuove funzionalità di accessibilità sono abilitate per impostazione predefinita per le applicazioni destinate a .NET Framework 4.7.1 o versioni successive. Oltre a ciò, le applicazioni destinate a una versione precedente di .NET Framework, ma eseguite in .NET Framework 4.7.1 o versioni successive, possono rifiutare esplicitamente comportamenti di accessibilità legacy (potendo così sfruttare i miglioramenti dell'accessibilità) aggiungendo opzioni all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione e impostandone il valore su `false`. Di seguito viene illustrato come acconsentire esplicitamente ai miglioramenti apportati all'accessibilità introdotti in .NET Framework 4.7.1:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Se si sceglie di acconsentire esplicitamente alle funzionalità di accessibilità in una versione successiva di .NET Framework, è necessario anche acconsentire esplicitamente alle funzionalità di versioni precedenti di .NET Framework. La configurazione dell'app per sfruttare i miglioramenti all'accessibilità sia in .NET Framework 4.7.1 che 4.7.2 richiede l'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a>Ripristino del comportamento legacy

Le applicazioni destinate alle versioni di .NET Framework a partire dalla 4.7.1 possono disabilitare le funzionalità di accessibilità aggiungendo opzioni all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione e impostandone il valore su `true`. Ad esempio, la configurazione seguente rifiuta esplicitamente le funzionalità di accessibilità introdotte in .NET Framework 4.7.2:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a>Nuove funzionalità di accessibilità in .NET Framework 4.7.2

.NET Framework 4.7.2 include nuove funzionalità di accessibilità nelle aree seguenti:

- [Windows Form](#winforms472)

- [Windows Presentation Foundation (WPF)](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a>Windows Form

**Colori definiti dal sistema operativo nei temi a contrasto elevato**

A partire da .NET Framework 4.7.2, Windows Forms usa colori definiti dal sistema operativo dei temi di contrasto elevato. Ciò influisce sui controlli seguenti:

- La freccia a discesa del controllo <xref:System.Windows.Forms.ToolStripDropDownButton>.

- I controlli <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con <xref:System.Windows.Forms.ButtonBase.FlatStyle> impostato su <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> o <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>. In precedenza, i colori dello sfondo e del testo selezionato non erano in contrasto e risultavano di difficile lettura.

- I controlli contenuti in un oggetto <xref:System.Windows.Forms.GroupBox> con la proprietà relativa <xref:System.Windows.Forms.Control.Enabled> impostata su `false`.

- I controlli <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> e <xref:System.Windows.Forms.ToolStripDropDownButton> che hanno un maggiore rapporto del contrasto di luminosità nella modalità a contrasto elevato.

- La proprietà <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> di <xref:System.Windows.Forms.DataGridViewLinkCell>.

**Miglioramenti di Assistente vocale**

A partire da .NET Framework 4.7.2, il supporto di Assistente vocale è stato migliorato come segue:

- Annuncia il valore della proprietà <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> mentre annuncia il testo di una classe <xref:System.Windows.Forms.ToolStripMenuItem>.

- Indica quando una classe <xref:System.Windows.Forms.ToolStripMenuItem> ha la proprietà <xref:System.Windows.Forms.Control.Enabled> impostata su `false`.

- Offre un feedback sullo stato di una casella di controllo quando la proprietà <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> è impostata su `true`.

- L'ordine di attivazione nella modalità di analisi dell'Assistente vocale rispetta l'ordine degli oggetti visivi dei controlli nella finestra di dialogo di download ClickOnce.

**Miglioramenti apportati a DataGridView**

A partire da .NET Framework 4.7.2, il controllo <xref:System.Windows.Forms.DataGridView> ha introdotto i miglioramenti di accessibilità seguenti:

- Le righe possono essere ordinate usando la tastiera. È possibile usare F3 per ordinare in base alla colonna corrente.

- Quando la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, l'intestazione di colonna cambia colore per indicare la colonna corrente man mano che l'utente si sposta tra le celle nella riga corrente tramite tabulazione.

- La proprietà <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> di un oggetto <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> restituisce il controllo padre corretto.

**Segnali visivi migliorati**

- I controlli <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con proprietà <xref:System.Windows.Forms.ButtonBase.Text> vuota visualizzano un indicatore di stato attivo quando ricevono lo stato attivo.

**Supporto migliorato per PropertyGrid**

- Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> ora restituiscono `true` per la proprietà <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> solo quando è abilitato un elemento PropertyGrid.

- Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> restituiscono `false` per la proprietà <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> solo quando un elemento PropertyGrid può essere modificato dall'utente.

**Navigazione tramite tastiera migliorata**

- Il controllo <xref:System.Windows.Forms.ToolStripButton> consente lo stato attivo quando è contenuto all'interno di una classe <xref:System.Windows.Forms.ToolStripPanel> con la proprietà <xref:System.Windows.Forms.ToolStripPanel.TabStop> impostata su `true`

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Modifiche ai controlli CheckBox e RadioButton**

In .NET Framework 4.7.1 e versioni precedenti i controlli <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> e <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> di WPF contengono oggetti visivi dello stato attivo incoerenti e non corretti nei temi classico e a contrasto elevato.  Questi problemi si verificano se i controlli non hanno impostato un contenuto.  La transizione tra i temi può risultare quindi confusa e diventa difficile visualizzare l'oggetto visivo con stato attivo.

In .NET Framework 4.7.2 questi oggetti visivi sono più coerenti tra i temi e possono essere visualizzati più facilmente nei temi classico e a contrasto elevato.

**Controlli WinForms ospitati in un'applicazione WPF**

Nel caso di un controllo WinForms ospitato in un'applicazione WPF in .NET Framework 4.7.1 e versioni precedenti, gli utenti non potevano uscire dal livello WinForms se il primo o l'ultimo controllo nel livello era il controllo <xref:System.Windows.Forms.Integration.ElementHost> di WPF. In .NET Framework 4.7.2 gli utenti possono uscire dal livello di WinForms.

Tuttavia, le applicazioni automatiche che si basano sullo stato attivo che non esce mai dal livello di WinForms potrebbero non funzionare più come previsto.

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Nuove funzionalità di accessibilità in .NET Framework 4.7.1

.NET Framework 4.7.1 include nuove funzionalità di accessibilità nelle aree seguenti:

- [Windows Presentation Foundation (WPF)](#wpf471)

- [Windows Form](#winforms471)

- [Controlli Web ASP.NET](#aspnet471)

- [Strumenti .NET SDK](#tools471)

- [Progettazione flussi di lavoro di Windows Workflow Foundation (WF)](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Miglioramenti per le utilità per la lettura dello schermo**

Se sono abilitati i miglioramenti per l'accessibilità, .NET Framework 4.7.1 include i miglioramenti seguenti che riguardano le utilità per la lettura dello schermo:

- In .NET Framework 4.7 e versioni precedenti, i controlli <xref:System.Windows.Controls.Expander> vengono annunciati come pulsanti dalle utilità per la lettura dello schermo. A partire da .NET Framework 4.7.1, sono annunciati correttamente come gruppi espandibili/comprimibili.

- In .NET Framework 4.7 e versioni precedenti, i controlli <xref:System.Windows.Controls.DataGridCell> vengono annunciati come "personalizzati". A partire da .NET Framework 4.7.1, sono annunciati correttamente come cella di griglia dati (localizzati).

- A partire da .NET Framework 4.7.1, le utilità per la lettura dello schermo annunciano il nome di un controllo <xref:System.Windows.Controls.ComboBox> modificabile.

- In .NET Framework 4.7 e versioni precedenti, i controlli <xref:System.Windows.Controls.PasswordBox> vengono annunciati come "Nessun elemento visualizzato" o il comportamento è in altro modo non corretto. Questo problema è stato risolto a partire da .NET Framework 4.7.1.

**Supporto di aree dinamiche UIAutomation**

Le utilità per la lettura dello schermo, come Assistente vocale, consentono di leggere il contenuto dell'interfaccia utente di un'applicazione, in genere annunciando tramite sintesi vocale il contenuto dell'interfaccia utente con lo stato attivo. Tuttavia, se un elemento dell'interfaccia utente viene modificato e non ha lo stato attivo, l'utente potrebbe non ricevere notifica e perdere informazioni importanti. Le aree dinamiche sono progettate per risolvere questo problema. Uno sviluppatore può usarle per informare l'utilità per la lettura dello schermo o qualsiasi altro client UIAutomation di un'importante modifica apportata a un elemento dell'interfaccia utente. L'utilità per la lettura dello schermo può quindi decidere come e quando informare l'utente di questa modifica.

Per supportare le aree dinamiche sono state aggiunte le API seguenti a WPF:

- I campi <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> che identificano la proprietà **LiveSetting** e l'evento **LiveRegionChanged**. Questi campi possono essere impostati tramite XAML.

- La proprietà associata **AutomationProperties.LiveSetting** che segnala all'utilità per la lettura dello schermo l'importanza della modifica dell'interfaccia utente per l'utente.

- La proprietà <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, che identifica la proprietà associata **AutomationProperties.LiveSetting**.

- Il metodo <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, di cui è possibile eseguire l'override per specificare un valore **LiveSetting**.

- I metodi <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, che consentono di ottenere e impostare un valore **LiveSetting**.

- L'enumerazione <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, che definisce le i valori **LiveSetting** possibili seguenti:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. L'elemento non invia notifiche se il contenuto dell'area dinamica è stato modificato.
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. L'elemento invia notifiche che non causano interruzioni se il contenuto dell'area dinamica è stato modificato.

   - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. L'elemento invia notifiche con interruzioni se il contenuto dell'area dinamica è stato modificato.

È possibile creare un'area dinamica impostando la proprietà **AutomationProperties.LiveSetting** sull'elemento di interesse, come illustrato nell'esempio seguente:

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

Quando vengono modificati i dati nell'area dinamica ed è necessario informarne un'utilità per la lettura dello schermo, deve essere generato un evento in modo esplicito, come illustrato nell'esempio seguente.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**Contrasto elevato**

A partire da .NET Framework 4.7.1, sono stati apportati miglioramenti relativi al contrasto elevato per vari controlli WPF, che sono ora visibili quando viene impostato il tema <xref:System.Windows.SystemParameters.HighContrast%2A>. Sono inclusi:

- Controllo <xref:System.Windows.Controls.Expander>

    L'oggetto visivo per lo stato attivo per il controllo <xref:System.Windows.Controls.Expander> è ora visibile. Anche gli oggetti visivi della tastiera per i controlli <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.RadioButton> sono visibili. Ad esempio:

    Prima: 

    ![Controllo Expander con lo stato attivo prima dei miglioramenti per l'accessibilità](media/expander-before.png)

    Dopo: 

    ![Controllo Expander con lo stato attivo dopo i miglioramenti per l'accessibilità](media/expander-after.png)

- Controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton>

    Il testo nei controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton> è ora più semplice da vedere quando viene selezionato nei temi a contrasto elevato. Ad esempio:

    Prima: 

    ![Pulsante di opzione con contrasto elevato con lo stato attivo prima dei miglioramenti per l'accessibilità](media/radio-button-before.png)

    Dopo: 

    ![Pulsante di opzione con contrasto elevato con lo stato attivo dopo i miglioramenti per l'accessibilità](media/radio-button-after.png)

- Controllo <xref:System.Windows.Controls.ComboBox>

    A partire da .NET Framework 4.7.1, il bordo di un controllo <xref:System.Windows.Controls.ComboBox> disabilitato ha lo stesso colore del testo disabilitato. Ad esempio:

    Prima: 

     ![Bordo e testo disabilitati del controllo ComboBox prima dei miglioramenti per l'accessibilità](media/combo-disabled-before.png)

    Dopo:   

     ![Bordo e testo disabilitati del controllo ComboBox dopo i miglioramenti per l'accessibilità](media/combo-disabled-after.png)

    Inoltre, i pulsanti con lo stato attivo e disabilitati usano il colore del tema corretto.

    Prima:

    ![Colori del tema dei pulsanti prima dei miglioramenti per l'accessibilità](media/button-themes-before.png) 

    Dopo: 

    ![Colori del tema dei pulsanti dopo i miglioramenti per l'accessibilità](media/button-themes-after.png) 

    Infine, in .NET Framework 4.7 e versioni precedenti, l'impostazione dello stile di un controllo <xref:System.Windows.Controls.ComboBox> su `Toolbar.ComboBoxStyleKey` rende invisibile la freccia a discesa. Questo problema è stato risolto a partire da .NET Framework 4.7.1. Ad esempio:

    Prima: 

    ![Toolbar.ComboBoxStyleKey prima dei miglioramenti per l'accessibilità](media/comboboxstylekey-before.png) 

    Dopo: 

    ![Toolbar.ComboBoxStyleKey dopo i miglioramenti per l'accessibilità](media/comboboxstylekey-after.png) 

- Controllo <xref:System.Windows.Controls.DataGrid>

    A partire da .NET Framework 4.7.1, la freccia dell'indicatore di ordinamento nei controlli <xref:System.Windows.Controls.DataGrid> usa ora i colori del tema corretti. Ad esempio:

    Prima: 

    ![Freccia dell'indicatore di ordinamento prima dei miglioramenti per l'accessibilità](media/sort-indicator-before.png) 

    Dopo:   

    ![Freccia dell'indicatore di ordinamento dopo i miglioramenti per l'accessibilità](media/sort-indicator-after.png) 

    Inoltre, in .NET Framework 4.7 e versioni precedenti, per lo stile di collegamento predefinito viene usato un colore non corretto al passaggio del mouse in modalità a contrasto elevato. Questo problema è stato risolto a partire da .NET Framework 4.7.1. Analogamente, le colonne della casella di controllo per i controlli <xref:System.Windows.Controls.DataGrid> usano i colori previsti per il riscontro dello stato attivo della tastiera a partire da .NET Framework 4.7.1.

    Prima: 

    ![Stile di collegamento predefinito DataGrid prima dei miglioramenti per l'accessibilità](media/default-link-style-before.png) 

    Dopo:    

    ![Stile di collegamento predefinito DataGrid dopo i miglioramenti per l'accessibilità](media/default-link-style-after.png) 

Per altre informazioni sui miglioramenti per l'accessibilità di WPF in .NET Framework 4.7.1, vedere [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf) (Miglioramenti per l'accessibilità in WPF).

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a>Miglioramenti per l'accessibilità di Windows Form

In .NET Framework 4.7.1 Windows Form (WinForms) include modifiche per l'accessibilità nelle aree seguenti.

**Miglioramento della visualizzazione in modalità a contrasto elevato**

A partire da .NET Framework 4.7.1, vari controlli WinForms offrono un rendering migliorato nelle modalità a contrasto elevato disponibili nel sistema operativo. Windows 10 ha cambiato i valori di alcuni colori di sistema a contrasto elevato e Windows Form si basa sul framework Win32 di Windows 10. Per risultati ottimali, usare la versione più recente di Windows e accettare le modifiche del sistema operativo più recenti aggiungendo un file app.manifest in un'applicazione di test e rimuovere il commento dalla riga del sistema operativo supportato Windows 10, in modo che abbia l'aspetto seguente:

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```

Alcuni esempi di modifiche per il contrasto elevato includono:

- I segni di spunta negli elementi <xref:System.Windows.Forms.MenuStrip> sono più facili da visualizzare.

- Gli elementi <xref:System.Windows.Forms.MenuStrip> disabilitati sono più facili da visualizzare quando sono selezionati.

- Il testo in un controllo <xref:System.Windows.Forms.Button> selezionato è contrastato rispetto al colore della selezione.

- Il testo disabilitato è più facile da leggere. Ad esempio:

    Prima:

    ![Testo disabilitato prima dei miglioramenti per l'accessibilità](media/wf-disabled-before.png) 

    Dopo:

    ![Testo disabilitato dopo i miglioramenti per l'accessibilità](media/wf-disabled-after.png) 

- Miglioramenti per il contrasto elevato nella finestra di dialogo di eccezione del thread.

**Supporto migliorato di Assistente vocale**

Windows Form in .NET Framework 4.7.1 include i seguenti miglioramenti per l'accessibilità per l'Assistente vocale:

- Il controllo <xref:System.Windows.Forms.MonthCalendar> è accessibile per l'Assistente vocale, così come da altri strumenti di automazione dell'interfaccia utente.

- Il controllo <xref:System.Windows.Forms.CheckedListBox> segnala all'Assistente vocale lo stato di selezione di un elemento, in modo che l'utente riceva notifica della modifica del valore di un elemento di elenco.

- Il controllo <xref:System.Windows.Forms.DataGridViewCell> segnala lo stato di sola lettura corretto all'Assistente vocale.

- Assistente vocale può ora leggere il testo <xref:System.Windows.Forms.ToolStripMenuItem> disabilitato, mentre in precedenza ignorava le voci di menu disabilitate.

**Supporto avanzato per i modelli di accessibilità UIAutomation**

A partire da .NET Framework 4.7.1, gli sviluppatori di strumenti di tecnologia per l'accessibilità possono sfruttare i modelli e le proprietà di accessibilità delle API comuni per numerosi controlli WinForms. Questi miglioramenti per l'accessibilità includono:

- <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ToolStripSplitButton> ora supportano il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> supporta ora il [modello di attivazione/disattivazione](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).

- Il controllo <xref:System.Windows.Forms.ToolStripItem> supporta la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> e il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- I controlli <xref:System.Windows.Forms.NumericUpDown> e <xref:System.Windows.Forms.DomainUpDown> supportano la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.

**Esperienza migliorata per il visualizzatore proprietà**

A partire da .NET Framework 4.7.1, Windows Form include:

- Migliori spostamenti tramite tastiera tra le varie finestre di selezione a discesa.
- Riduzione dei punti di tabulazione non necessari.
- Segnalazione migliore dei tipi di controllo.
- Comportamento migliorato dell'Assistente vocale.

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a>Controlli Web ASP.NET

A partire da .NET Framework 4.7.1 e Visual Studio 2017 15.3, in ASP.NET è stato migliorato il funzionamento dei controlli Web ASP.NET con tecnologia di accessibilità in Visual Studio. Le modifiche includono quanto segue:

- Modifiche per implementare criteri di accessibilità dell'interfaccia utente mancanti nei controlli, come la finestra di dialogo **Aggiungi campo** nella procedura guidata **Visualizzazione dettagli** o la finestra di dialogo **Configura ListView** nella procedura guidata **ListView**.

- Modifiche per migliorare la visualizzazione nella modalità a contrasto elevato, ad esempio l'**Editor campi del pager di dati**.

- Modifiche per migliorare la navigazione tramite tastiera per controlli, come la finestra di dialogo **Campi** nella procedura guidata **Modifica campi del pager** del controllo DataPager, la finestra di dialogo **Configura ObjectContext** o la finestra di dialogo **Configura selezione dati** della procedura guidata **Configura origine dati**.

<a name="tools471"></a>

### <a name="net-sdk-tools"></a>Strumenti .NET SDK

Lo [strumento Editor di configurazione (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) e lo [strumento Visualizzatore di tracce (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) sono stati migliorati correggendo vari problemi di accessibilità. Molti erano problemi di lieve entità, come ad esempio un nome non definito o alcuni criteri dell'automazione interfaccia utente non implementati correttamente. È possibile che molti utenti non si siano accorti di questi valori non corretti. I clienti che usano le assistive technology, ad esempio le utilità per la lettura dello schermo, troveranno invece questi strumenti SDK più accessibili.

Tali miglioramenti modificano alcuni comportamenti precedenti, ad esempio l'ordine di attivazione della tastiera.

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a>Progettazione flussi di lavoro di Windows Workflow Foundation (WF)

Le modifiche all'accessibilità in Progettazione flussi di lavoro includono quanto segue:

- L'ordine di tabulazione viene modificato da sinistra a destra e dall'alto verso il basso in alcuni controlli:

  - La finestra di inizializzazione della correlazione in cui impostare i dati di correlazione per l'attività <xref:System.ServiceModel.Activities.InitializeCorrelation>.

  - La finestra di definizione del contenuto per le attività <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>.

- Altre funzioni sono disponibili tramite tastiera:

  - Quando vengono modificate le proprietà di un'attività, i gruppi delle proprietà possono essere compressi tramite tastiera la prima volta che hanno lo stato attivo.

  - Le icone di avviso sono accessibili dalla tastiera.

  - Il pulsante **Altre proprietà** nella finestra **Proprietà** è accessibile dalla tastiera.

  - Tramite tastiera gli utenti possono accedere agli elementi dell'intestazione nei riquadri **Argomenti** e **Variabili** in Progettazione flussi di lavoro.

- Maggiore visibilità degli elementi con stato attivo, ad esempio quando:

  - Aggiunta di righe alle griglie di dati usate in Progettazione flussi di lavoro e in ActivityDesigner.

  - Tabulazione all'interno dei campi nelle attività <xref:System.ServiceModel.Activities.ReceiveReply> e <xref:System.ServiceModel.Activities.SendReply>.

  - Impostazione di valori predefiniti per variabili o argomenti

- Le utilità per la lettura dello schermo ora possono riconoscere correttamente:

  - Set di punti di interruzione in Progettazione flussi di lavoro.

  - Attività <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> e <xref:System.ServiceModel.Activities.CorrelationScope>.
  - Contenuto dell'attività <xref:System.ServiceModel.Activities.Receive>.

  - Tipo di destinazione per l'attività <xref:System.Activities.Statements.InvokeMethod>.

  - Casella combinata Eccezione e sezione Finally nell'attività <xref:System.Activities.Statements.TryCatch>.

  - Casella combinata Tipo di messaggio, barra di divisione nella finestra Aggiungi inizializzatori di correlazione, finestra Content Definition (Definizione contenuto) e finestra Definizione di CorrelatesOn nelle attività di messaggistica (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>).

  - Transizioni della macchina a uno stato e destinazioni delle transazioni.

  - Annotazioni e connettori nelle attività <xref:System.Activities.Statements.FlowDecision>.

  - Menu di scelta rapida per le attività.

  - Editor di valori di proprietà, pulsante Cancella ricerca, pulsanti di ordinamento Per categoria e In ordine alfabetico e finestra di dialogo Editor espressioni nella griglia delle proprietà.

  - Percentuale di zoom in Progettazione flussi di lavoro.

  - Separatore nelle attività <xref:System.Activities.Statements.Parallel> e <xref:System.Activities.Statements.Pick>.

  - Attività <xref:System.Activities.Statements.InvokeDelegate>.

  - Finestra Seleziona tipi per le attività di dizionario (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` e così via).

  - Finestra Cerca e seleziona un tipo .NET.

  - Navigazioni in Progettazione flussi di lavoro.

- Gli utenti che usano i temi a contrasto elevato noteranno molti miglioramenti nella visibilità di Progettazione flussi di lavoro e nei relativi controlli, ad esempio rapporti di contrasto più definiti tra gli elementi e caselle di selezione più evidenti per gli elementi con lo stato attivo.

## <a name="see-also"></a>Vedere anche

- [Novità di .NET Framework](whats-new.md)
