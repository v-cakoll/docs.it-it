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
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Nuove funzionalità di accessibilità in .NET Framework

.NET Framework mira a rendere le applicazioni più accessibile per gli utenti. Funzionalità di accessibilità consentono di offrire un'esperienza appropriata per gli utenti di Assistive Technology. A partire da .NET Framework 4.7.1, .NET Framework include un numero elevato di miglioramenti di accessibilità che consentono agli sviluppatori di creare applicazioni di accessibilità. 

Le nuove funzionalità di accessibilità sono abilitati per impostazione predefinita per le applicazioni destinate a .NET Framework 4.7.1 o successive. Inoltre, applicazioni di destinazione una versione precedente di .NET Framework, ma sono in esecuzione in .NET Framework 4.7.1 o versioni successive è possono scegliere di comportamenti di accessibilità legacy (e in tal modo optare per i miglioramenti di accessibilità in .NET Framework 4.7.1) da aggiungendo il seguente parametro per il [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento il [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'applicazione. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Analogamente, le applicazioni destinate alle versioni di .NET Framework a partire da 4.7.1 possono disabilitare le funzionalità di accessibilità aggiungendo la seguente opzione per il [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento il [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'applicazione. 

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

**Miglioramenti di lettura dello schermo**

Se sono abilitati i miglioramenti di accessibilità, .NET Framework 4.7.1 include i miglioramenti seguenti che interessano gli screen reader:

- In .NET Framework 4.7 e versioni precedenti, <xref:System.Windows.Controls.Expander> controlli annunciati lettura dello schermo come pulsanti. A partire da .NET Framework 4.7.1, sono correttamente annunciati come gruppi espandibile/comprimibile.

- In .NET Framework 4.7 e versioni precedenti, <xref:System.Windows.Controls.DataGridCell> controlli annunciati lettura dello schermo come "custom". A partire da .NET Framework 4.7.1, sono ora correttamente annunciati come cella della griglia di dati (localizzato).
 
- A partire da .NET Framework 4.7.1, gli screen reader annunciare il nome di un modificabile <xref:System.Windows.Controls.ComboBox>.

- In .NET Framework 4.7 e versioni precedenti, <xref:System.Windows.Controls.PasswordBox> controlli sono stati annunciati come "Nessun elemento nella vista" o ha un comportamento in caso contrario non corretto. Questo problema è risolto a partire da .NET Framework 4.7.1.     

**Supporto UIAutomation LiveRegion**

Lettura dello schermo, ad esempio persone Guida Assistente vocale legge il contenuto dell'interfaccia utente di un'applicazione, in genere dall'output di sintesi vocale del contenuto dell'interfaccia utente che ha lo stato attivo. Tuttavia, se un elemento dell'interfaccia utente viene modificato e non ha lo stato attivo, l'utente non può essere comunicata e potrebbe non essere implementato informazioni importanti. Le aree in tempo reale hanno lo scopo di risolvere il problema. Uno sviluppatore può utilizzarli per informare la lettura dello schermo o qualsiasi altro client UIAutomation un'importante modifica apportata a un elemento dell'interfaccia utente. La lettura dello schermo può quindi decidere come e quando per informare l'utente di questa modifica. 

Per supportare le aree in tempo reale, le API seguenti sono state aggiunte a WPF:

- Il <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> campi che identificano il **LiveSetting** proprietà e **LiveRegionChanged** evento. Possono essere configurati per tramite XAML.

- Il **AutomationProperties.LiveSetting** proprietà collegata, che indica la lettura dello schermo di importanza della modifica dell'interfaccia utente per l'utente.

- Il <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> proprietà che identifica il **AutomationProperties.LiveSetting** proprietà associata.
 
- Il <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> (metodo), che può essere sostituito per fornire un **LiveSetting** valore.

- Il <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> i metodi, ottenere e impostare un **LiveSetting** valore.
 
- Il <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumerazione, che definisce le seguenti possibili **LiveSetting** valori:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. L'elemento non invia notifiche se è stato modificato il contenuto dell'area in tempo reale.   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. L'elemento invia notifiche che non causano interruzioni se il contenuto dell'area dinamica è stato modificato.   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. L'elemento invia notifiche con interruzioni se il contenuto dell'area dinamica è stato modificato.   

È possibile creare un LiveRegion impostando il **AutomationProperties.LiveSetting** proprietà sull'elemento di interesse, come illustrato nell'esempio seguente:   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

Quando vengono modificati i dati nell'area in tempo reale ed è necessario informare lettura dello schermo, in modo esplicito un evento viene generato, come illustrato nell'esempio seguente.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**Contrasto elevato**

A partire da .NET Framework 4.7.1, sono stati apportati miglioramenti contrasto elevato per vari controlli WPF. Sono ora visibili quando il <xref:System.Windows.SystemParameters.HighContrast%2A> tema è impostato. tra cui:

- Controllo <xref:System.Windows.Controls.Expander>

    Lo stato attivo per il <xref:System.Windows.Controls.Expander> controllo è ora visibile. Gli oggetti visivi della tastiera per <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, e <xref:System.Windows.Controls.RadioButton> anche i controlli sono visibili. Ad esempio:

    Prima: 
    
    ![Controllo Expander con lo stato attivo prima di miglioramenti di accessibilità](media/expander-before.png)

    Dopo: 

    ![Controllo Expander con lo stato attivo dopo i miglioramenti di accessibilità](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox>e <xref:System.Windows.Controls.RadioButton> controlli
 
    Il testo di <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton> controlli è ora più semplice vedere quando selezionato in temi a contrasto elevato. Ad esempio:

    Prima: 

    ![Pulsante di opzione Contrasto elevato con lo stato attivo prima di miglioramenti di accessibilità](media/radio-button-before.png)
    
    Dopo: 

    ![Pulsante di opzione Contrasto elevato con lo stato attivo dopo i miglioramenti di accessibilità](media/radio-button-after.png)

- Controllo <xref:System.Windows.Controls.ComboBox>
 
    A partire da .NET Framework 4.7.1, il bordo di disattivato <xref:System.Windows.Controls.ComboBox> controllo è sullo stesso colore testo disabilitato. Ad esempio:
    
    Prima: 

     ![Casella combinata disabilitato bordo e il testo prima di miglioramenti di accessibilità](media/combo-disabled-before.png)

    Dopo:   

     ![Casella combinata disabilitato bordo e il testo dopo i miglioramenti di accessibilità](media/combo-disabled-after.png)

    Inoltre, i pulsanti con lo stato attivo e disabilitati utilizzano il colore del tema corretto.

    Prima:

    ![Colori del tema pulsante prima di miglioramenti di accessibilità](media/button-themes-before.png) 
    
    Dopo: 

    ![Colori del tema pulsante dopo i miglioramenti di accessibilità](media/button-themes-after.png) 

    Infine, in .NET Framework 4.7 e versioni precedenti, l'impostazione un <xref:System.Windows.Controls.ComboBox> stile del controllo `Toolbar.ComboBoxStyleKey` ha causato la freccia a discesa sia invisibile. Questo problema è risolto a partire da .NET Framework 4.7.1. Ad esempio:

    Prima: 

    ![Toolbar.ComboBoxStyleKey prima di miglioramenti di accessibilità](media/comboboxstylekey-before.png) 
    
    Dopo: 

    ![Toolbar.ComboBoxStyleKey dopo i miglioramenti di accessibilità](media/comboboxstylekey-after.png) 

- Controllo <xref:System.Windows.Controls.DataGrid>

    A partire da .NET Framework 4.7.1, la freccia di ordinamento indicatore in <xref:System.Windows.Controls.DataGrid> controlla ora utilizza correzione i colori del tema. Ad esempio:

    Prima: 

    ![Freccia di ordinamento indicatore prima di miglioramenti di accessibilità](media/sort-indicator-before.png) 
    
    Dopo:   
 
    ![Freccia di ordinamento indicatore dopo i miglioramenti di accessibilità](media/sort-indicator-after.png) 
    
    Inoltre, in .NET Framework 4.7 e versioni precedenti, lo stile di collegamento predefinito modificato in un colore non corretto al passaggio del mouse in modalità a contrasto elevato. Questo viene risolto a partire da .NET Framework 4.7.1. Analogamente, <xref:System.Windows.Controls.DataGrid> colonne casella di controllo vengono utilizzati i colori previsto per il feedback lo stato attivo della tastiera a partire da .NET Framework 4.7.1.

    Prima: 

    ![Stile di collegamento predefinito DataGrid prima di miglioramenti di accessibilità](media/default-link-style-before.png) 
 
    Dopo:    
  
    ![Stile di collegamento predefinito DataGrid dopo i miglioramenti di accessibilità](media/default-link-style-after.png)  

Per ulteriori informazioni sui miglioramenti di accessibilità WPF in .NET Framework 4.7.1, vedere [miglioramenti di accessibilità in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

## <a name="windows-forms-accessibility-improvements"></a>Miglioramenti di accessibilità di Windows Form

In .NET Framework 4.7.1 Windows Form (Winform) include le modifiche di accesso nelle aree seguenti.

**Miglioramento della visualizzazione in modalità a contrasto elevato**

A partire da .NET Framework 4.7.1, vari controlli Windows Form offrono migliorate per il rendering in modalità di contrasto elevato disponibili nel sistema operativo. I valori per alcuni colori di sistema di contrasto elevato è stato modificato da Windows 10 e Windows Form è basato su Windows 10 Win32 framework. Per risultati ottimali, eseguire la versione più recente di Windows e consente di partecipare alle modifiche del sistema operativo più recente mediante l'aggiunta di che un file app. manifest in un'applicazione di test e un commento di Windows 10 supportate riga del sistema operativo in modo che esegua le operazioni seguenti:

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
Alcuni esempi di modifiche di contrasto elevato:

- Segni di spunta in <xref:System.Windows.Forms.MenuStrip> gli elementi sono più facili da visualizzare.

- Quando selezionato, disabilitato <xref:System.Windows.Forms.MenuStrip> gli elementi sono più facili da visualizzare.

- Testo in un determinato <xref:System.Windows.Forms.Button> controllare contrasta con il colore della selezione.

- Testo disabilitato è più facile da leggere. Ad esempio:

    Prima:

    ![Testo disabilitato prima di miglioramenti di accessibilità](media/wf-disabled-before.png) 

    Dopo:

    ![Testo disabilitato dopo i miglioramenti di accessibilità](media/wf-disabled-after.png) 

- Miglioramenti di contrasto elevato nella finestra di dialogo di eccezione del Thread.

**Supporto migliorato di Assistente vocale**

Windows Form in .NET Framework 4.7.1 include i seguenti miglioramenti di accessibilità per l'Assistente vocale:

- Il <xref:System.Windows.Forms.MonthCalendar> può accedere al controllo per l'Assistente vocale, nonché da altri strumenti di automazione interfaccia utente.

- Il <xref:System.Windows.Forms.CheckedListBox> controllo notifica dell'Assistente vocale quando lo stato di controllo di un elemento è stato modificato in modo che l'utente viene notificato che è stato modificato il valore di un elemento elenco.
 
- Il <xref:System.Windows.Forms.DataGridViewCell> controllo segnala lo stato di sola lettura corretto per l'Assistente vocale.
 
- Assistente vocale può ora leggere disabilitato <xref:System.Windows.Forms.ToolStripMenuItem> testo, mentre in precedenza ignorando le voci di menu disabilitata.

**Supporto avanzato per modelli di accessibilità UIAutomation**

A partire da .NET Framework 4.7.1, gli sviluppatori di strumenti di accessibilità della tecnologia possono sfruttare modelli di accessibilità di API comuni e le proprietà per numerosi controlli Windows Form. Questi miglioramenti di accessibilità includono:

- Il <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ToolStripSplitButton> supportano ora il [patternExpandCollapse/](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
 
- Il <xref:System.Windows.Forms.DataGridViewCheckBoxCell> supporta ora il [pattern toggle](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).
 
- Il <xref:System.Windows.Forms.ToolStripItem> controllo supporta il <xref:System.Windows.Automation.AutomationElement.Name> proprietà e [patternExpandCollapse/](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- Il <xref:System.Windows.Forms.NumericUpDown> e <xref:System.Windows.Forms.DomainUpDown> controlli supportano il <xref:System.Windows.Automation.automationElement.Name> proprietà.

**Proprietà una migliore esperienza di browser**

A partire da .NET Framework 4.7.1, Windows Form include:

- Una migliore navigazione tramite tastiera le varie finestre di selezione elenco a discesa.
- Riduzione dei punti di tabulazione non necessari.
- Meglio reporting dei tipi di controllo.
- Comportamento migliorato Assistente vocale.
 
## <a name="see-also"></a>Vedere anche
[Novità di .NET Framework](whats-new.md)   
 