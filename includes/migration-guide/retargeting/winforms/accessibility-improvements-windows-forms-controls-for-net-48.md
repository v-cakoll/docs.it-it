---
ms.openlocfilehash: e528a41748d9353c96d443f68e15e7a98ee7f4ae
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616265"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-48"></a>Miglioramenti di accessibilità nei controlli Windows Forms per .NET 4.8

#### <a name="details"></a>Dettagli

Il funzionamento del framework di Windows Forms è in continuo miglioramento grazie alle tecnologie di accessibilità al servizio dei clienti di Windows Forms. Sono incluse le modifiche seguenti:

- Modifiche per migliorare la visualizzazione durante la modalità a contrasto elevato.
- Modifiche all'interazione con l'Assistente vocale.
- Modifiche alla gerarchia accessibile grazie al miglioramento della navigazione attraverso l'albero di automazione interfaccia utente.

#### <a name="suggestion"></a>Suggerimento

**Come acconsentire esplicitamente o escludere queste modifiche** Per consentire all'applicazione di trarre vantaggio da queste modifiche, è necessario che l'applicazione venga eseguita nel .NET Framework 4,8. L'applicazione può acconsentire esplicitamente a queste modifiche in uno dei modi seguenti:

- Viene ricompilata per usare .NET Framework 4.8. Queste modifiche di accessibilità sono abilitate per impostazione predefinita nelle applicazioni Windows Forms destinate a .NET Framework 4.8.
- È destinata a .NET Framework 4.7.2 o versione precedente e rifiuta esplicitamente i comportamenti di accessibilità legacy aggiungendo l'[opzione di AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione `<runtime>` del file di configurazione dell'app e impostandola su `false`, come illustrato nell'esempio seguente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
  </runtime>
</configuration>
```

Si noti che per acconsentire esplicitamente alle funzionalità di accessibilità aggiunte in .NET Framework 4.8, è anche necessario acconsentire esplicitamente alle funzionalità di accessibilità di .NET Framework 4.7.1 e 4.7.2. Le applicazioni destinate a .NET Framework 4.8 che vogliono mantenere il comportamento di accessibilità legacy possono acconsentire esplicitamente all'uso delle funzionalità di accessibilità legacy impostando in modo esplicito questa opzione di AppContext su `true`.Per abilitare il supporto della chiamata di ToolTip da tastiera è necessario aggiungere una riga `Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false` al valore di AppContextSwitchOverrides:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false" />
```

Si noti che l'abilitazione di questa funzionalità richiede di acconsentire esplicitamente alle funzionalità di accessibilità di .NET Framework 4.7.1 - 4.8 menzionate in precedenza. Tenere presente anche che, se non si è acconsentito esplicitamente alle funzionalità di accessibilità ma l'opzione di visualizzazione delle descrizioni dei comandi è abilitata, verrà generata un'eccezione di runtime <xref:System.NotSupportedException> al primo accesso a queste funzionalità. Il messaggio di eccezione indica che i tasti di scelta rapida richiedono miglioramenti per l'accessibilità di livello 3 da abilitare.

**Uso di colori definiti dal sistema operativo nei temi a contrasto elevato**

- Temi a contrasto elevato migliorati.

**Supporto migliorato di Assistente vocale**

- L'assistente vocale ora annuncia la direzione di ordinamento di <xref:System.Windows.Forms.DataGridViewColumn> quando annuncia il nome accessibile di un oggetto <xref:System.Windows.Forms.DataGridViewCell>.

**Supporto dell'accessibilità al controllo CheckedListBox migliorato**

- Supporto dell'assistente vocale per il controllo <xref:System.Windows.Forms.CheckedListBox> migliorato. Quando si passa al controllo <xref:System.Windows.Forms.CheckedListBox> usando la tastiera, l'assistente vocale evidenzia l'elemento <xref:System.Windows.Forms.CheckedListBox> e lo annuncia.
- Il controllo CheckedListBox vuoto ora ha un rettangolo di attivazione disegnato per il primo elemento virtuale quando il controllo viene evidenziato.

**Supporto dell'accessibilità al controllo ComboBox migliorato**

- Abilitato il supporto di automazione interfaccia utente per il controllo <xref:System.Windows.Forms.ComboBox>, con la possibilità di usare le notifiche e altre funzionalità di automazione interfaccia utente.
**Supporto migliorato per l'accessibilità di DataGridView**

- Abilitato il supporto di automazione interfaccia utente per il controllo <xref:System.Windows.Forms.DataGridView>, con la possibilità di usare le notifiche e altre funzionalità di automazione interfaccia utente.
- L'elemento di automazione interfaccia utente che corrisponde a <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl> o a <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl> è ora un elemento figlio della cella di modifica corrispondente.

**Supporto dell'accessibilità al controllo LinkLabel migliorato**

- <xref:System.Windows.Forms.LinkLabel>Accessibilità del controllo migliorata: Assistente vocale annuncia lo stato disabilitato per il collegamento se il <xref:System.Windows.Forms.LinkLabel> controllo corrispondente è disabilitato.

**Supporto dell'accessibilità al controllo Improved ProgressBar migliorato**

- Abilitato il supporto di automazione interfaccia utente per il controllo <xref:System.Windows.Forms.ProgressBar>, con la possibilità di usare le notifiche e altre funzionalità di automazione interfaccia utente. Gli sviluppatori possono ora usare le notifiche di automazione interfaccia utente che l'assistente vocale può annunciare per indicare lo stato di avanzamento.
Per una panoramica degli eventi di automazione interfaccia utente Panoramica, inclusi gli eventi di notifica di automazione interfaccia utente, vedere [Cenni preliminari sugli eventi](https://docs.microsoft.com/windows/desktop/WinAuto/uiauto-eventsoverview)di automazione interfaccia utente.

**Miglioramento del supporto per l'accessibilità PropertyGrid**

- Abilitato il supporto di automazione interfaccia utente per il controllo <xref:System.Windows.Forms.PropertyGrid>, con la possibilità di usare le notifiche e altre funzionalità di automazione interfaccia utente.
- L'elemento di automazione interfaccia utente che corrisponde alla proprietà attualmente modificata è ora un elemento figlio dell'elemento di automazione interfaccia utente dell'elemento della proprietà corrispondente.
- L'elemento della proprietà di automazione interfaccia utente è ora un elemento figlio dell'elemento della categoria corrispondente, se il controllo padre <xref:System.Windows.Forms.PropertyGrid> è impostato sulla visualizzazione per categorie.

**Supporto per il controllo ToolStrip migliorato**

- Abilitato il supporto di automazione interfaccia utente per il controllo <xref:System.Windows.Forms.ToolStrip>, con la possibilità di usare le notifiche e altre funzionalità di automazione interfaccia utente.
- Navigazione negli elementi <xref:System.Windows.Forms.ToolStrip> migliorata.
- Nella modalità elementi l'evidenziazione dell'assistente vocale non scompare e non viene applicata agli elementi nascosti.

**Segnali visivi migliorati**

- Un controllo <xref:System.Windows.Forms.CheckedListBox> vuoto ora visualizza un indicatore quando viene evidenziato.
Nota: il supporto di automazione interfaccia utente è abilitato per i controlli in fase di esecuzione, ma non viene usato in fase di progettazione. Per una panoramica dell'automazione interfaccia utente, vedere [Panoramica di automazione interfaccia utente](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).

**Richiamo delle descrizioni comando dei controlli con la tastiera**

- Le descrizioni comando dei controlli ora possono essere richiamate evidenziando il controllo con la tastiera. Questa funzionalità deve essere abilitata in modo esplicito per l'applicazione. vedere la sezione ** &quot; come acconsentire o rifiutare le &quot; modifiche**.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Principale       |
| Version | 4.8         |
| Type    | Ridestinazione |
