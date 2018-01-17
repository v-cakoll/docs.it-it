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
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Nuove funzionalità di accessibilità in .NET Framework

Uno degli obiettivi di .NET Framework è rendere le applicazioni più accessibili per gli utenti. Le funzionalità di accessibilità consentono a un'applicazione di offrire un'esperienza appropriata per gli utenti di assistive technology. A partire da .NET Framework 4.7.1, .NET Framework include numerosi miglioramenti per l'accessibilità che consentono agli sviluppatori di creare applicazioni accessibili. 

Le nuove funzionalità di accessibilità sono abilitate per impostazione predefinita per le applicazioni destinate a .NET Framework 4.7.1 o versioni successive. Inoltre, le applicazioni destinate a una versione precedente di .NET Framework, ma eseguite in .NET Framework 4.7.1 o versioni successive possono rifiutare in modo esplicito comportamenti di accessibilità legacy (accettando quindi i miglioramenti per l'accessibilità in .NET Framework 4.7.1) aggiungendo l'opzione seguente all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Analogamente, le applicazioni destinate alle versioni di .NET Framework a partire da 4.7.1 possono disabilitare le funzionalità di accessibilità aggiungendo la seguente opzione all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Nuove funzionalità di accessibilità in .NET Framework 4.7.1

.NET Framework 4.7.1 include nuove funzionalità di accessibilità nelle aree seguenti:

- [Windows Presentation Foundation (WPF)](#windows-presentation-foundation-wpf)

- [Windows Form](#windows-forms-accessibility-improvements)

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

- La proprietà associata **AutomationProperties.LiveSetting**, che segnala all'utilità per la lettura dello schermo l'importanza della modifica dell'interfaccia utente per l'utente.

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

    L'oggetto visivo per lo stato attivo per il controllo <xref:System.Windows.Controls.Expander> è ora visibile. Anche gli oggetti visivi della tastiera per i controlli <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.RadioButton> sono visibili. Ad esempio:

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

## <a name="windows-forms-accessibility-improvements"></a>Miglioramenti per l'accessibilità di Windows Form

In .NET Framework 4.7.1 Windows Form (WinForms) include modifiche per l'accessibilità nelle aree seguenti.

**Miglioramento della visualizzazione in modalità a contrasto elevato**

A partire da .NET Framework 4.7.1, vari controlli WinForms offrono un rendering migliorato nelle modalità a contrasto elevato disponibili nel sistema operativo. Windows 10 ha cambiato i valori di alcuni colori di sistema a contrasto elevato e Windows Form si basa sul framework Win32 di Windows 10. Per risultati ottimali, usare la versione più recente di Windows e accettare le modifiche del sistema operativo più recenti aggiungendo un file app.manifest in un'applicazione di test e rimuovere il commento dalla riga del sistema operativo supportato Windows 10, in modo che sia come segue:

```xml
<!– Windows 10 –>
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
 
## <a name="see-also"></a>Vedere anche
[Novità di .NET Framework](whats-new.md)   
 