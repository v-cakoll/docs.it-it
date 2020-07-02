---
ms.openlocfilehash: c8e1c91f4fee8aa896b6617c815fe2a4b6d22f2a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614887"
---
### <a name="accessibility-improvements-in-windows-forms-controls"></a>Miglioramenti di accessibilità nei controlli Windows Form

#### <a name="details"></a>Dettagli

In Windows Form è stato migliorato il funzionamento con le tecnologie di accessibilità per supportare al meglio i clienti Windows Form. A partire da .NET Framework 4.7.1, i miglioramenti includono le modifiche seguenti:

- Modifiche per migliorare la visualizzazione durante la modalità a contrasto elevato.
- Modifiche per migliorare l'esperienza di visualizzazione delle proprietà. I miglioramenti di visualizzazione delle proprietà includono:
- Migliori spostamenti tramite tastiera tra le varie finestre di selezione a discesa.
- Riduzione delle tabulazioni non necessarie.
- Segnalazione migliore dei tipi di controllo.
- Comportamento migliorato dell'Assistente vocale.
- Modifiche per implementare pattern di accessibilità dell'interfaccia utente mancanti nei controlli.

#### <a name="suggestion"></a>Suggerimento

**Come acconsentire esplicitamente o escludere queste modifiche** Per consentire all'applicazione di trarre vantaggio da queste modifiche, è necessario eseguirla nel .NET Framework 4.7.1 o versione successiva. L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:

- Viene ricompilata per usare .NET Framework 4.7.1. Queste modifiche di accessibilità sono abilitate per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.1 o versione successiva.
- I comportamenti di accessibilità legacy vengono rifiutati aggiungendo l'[opzione di AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

Le applicazioni che usano .NET Framework 4.7.1 o versione successiva e che vogliono mantenere il comportamento di accessibilità legacy possono scegliere di usare le funzionalità di accessibilità legacy impostando in modo esplicito questa opzione di AppContext su `true`.<p/>Per una panoramica dell'automazione interfaccia utente, vedere [Panoramica di automazione interfaccia utente](~/docs/framework/ui-automation/ui-automation-overview.md).<p/>**Aggiunta del supporto per i pattern e le proprietà dell'automazione interfaccia utente**<br/>I client di accessibilità possono usufruire delle nuove funzionalità di accessibilità di Windows Form usando i comuni pattern di chiamata descritti pubblicamente. Questi pattern non sono specifici di Windows Form. Ad esempio, i client di accessibilità possono chiamare il metodo QueryInterface nell'interfaccia IAccessible (MAAS) per ottenere un'interfaccia IServiceProvider. Se questa interfaccia è disponibile, i client possono usare il suo metodo QueryService per richiedere un'interfaccia IAccessibleEx. Per altre informazioni, vedere [Using IAccessibleEx from a Client](https://docs.microsoft.com/windows/desktop/WinAuto/using-iaccessibleex-from-a-client) (Uso di IAccessibleEx da un client). A partire da .NET Framework 4.7.1, IServiceProvider e [IAccessibleEx](https://docs.microsoft.com/windows/desktop/WinAuto/iaccessibleex) (dove applicabile) sono disponibili per gli oggetti di accessibilità Windows Form.<p/>.NET Framework 4.7.1 aggiunge supporto per le proprietà e i pattern dell'automazione interfaccia utente seguenti:

- I controlli <xref:System.Windows.Forms.ToolStripSplitButton> e <xref:System.Windows.Forms.ComboBox> supportano il [pattern di espansione e comprensione](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Il controllo <xref:System.Windows.Forms.ToolStripMenuItem> ha un valore della proprietà [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) di <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- Il controllo <xref:System.Windows.Forms.ToolStripItem> supporta la proprietà <xref:System.Windows.Automation.AutomationElement.NameProperty> e il [pattern di espansione e comprensione](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Il controllo <xref:System.Windows.Forms.ToolStripDropDownItem> supporta <xref:System.Windows.Forms.AccessibleEvents> che indica StateChange e NameChange quando l'elenco a discesa è espanso o compresso.
- Il controllo <xref:System.Windows.Forms.ToolStripDropDownButton> ha un valore della proprietà [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) di <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- Il controllo <xref:System.Windows.Forms.DataGridViewCheckBoxCell> supporta <xref:System.Windows.Automation.TogglePattern>.
- I controlli <xref:System.Windows.Forms.NumericUpDown> e <xref:System.Windows.Forms.DomainUpDown> supportano la proprietà <xref:System.Windows.Automation.AutomationElement.NameProperty> e hanno un valore [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md) di <xref:System.Windows.Automation.ControlType.Spinner?displayProperty=nameWithType>.</p>
**Miglioramenti al controllo PropertyGrid** Il .NET Framework 4.7.1 aggiunge i miglioramenti seguenti al controllo PropertyBrowser:

- Il pulsante **Dettagli** nella finestra di dialogo di errore visualizzata viene immesso un valore non corretto nel controllo <xref:System.Windows.Forms.PropertyGrid> supporta il [pattern di espansione e comprensione](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md), le notifiche della modifica di stato e nome e una proprietà [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) con un valore di <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- Il riquadro del messaggio visualizzato quando il pulsante **Dettagli** nella finestra di dialogo di errore viene selezionato ora è accessibile tramite tastiera e consente all'Assistente vocale di annunciare il contenuto del messaggio di errore.
- L'oggetto <xref:System.Windows.Forms.AccessibleRole> di righe nel controllo <xref:System.Windows.Forms.PropertyGrid> è stato modificato da &quot;Riga&quot; a &quot;Cella&quot;. La cella esegue il mapping all'oggetto &quot;DataItem&quot; di ControlType in Automazione interfaccia utente, che consente di supportare tasti di scelta rapida appropriati e annunci dell'Assistente vocale.
- Le righe del controllo <xref:System.Windows.Forms.PropertyGrid> che rappresentano gli elementi intestazione quando il controllo <xref:System.Windows.Forms.PropertyGrid> ha una proprietà <xref:System.Windows.Forms.PropertyGrid.PropertySort> impostata su <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> hanno un valore della proprietà [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) di <xref:System.Windows.Automation.ControlType.Button?displayProperty=nameWithType>.
- Le righe del controllo <xref:System.Windows.Forms.PropertyGrid> che rappresentano gli oggetti intestazione quando il controllo <xref:System.Windows.Forms.PropertyGrid> ha una proprietà <xref:System.Windows.Forms.PropertyGrid.PropertySort> impostata su <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> supportano il [pattern di espansione e comprensione](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Miglioramento della navigazione tramite tastiera tra griglia e barra degli strumenti superiore. Premendo &quot;MAIUSC+TAB&quot; ora si seleziona il primo pulsante della barra degli strumenti, anziché l'intera barra degli strumenti.
- I controlli <xref:System.Windows.Forms.PropertyGrid> visualizzati in modalità a contrasto elevato consentono di disegnare un rettangolo di selezione intorno al pulsante della barra degli strumenti che corrisponde al valore della proprietà <xref:System.Windows.Forms.PropertyGrid.PropertySort> corrente.
- I controlli <xref:System.Windows.Forms.PropertyGrid> visualizzati in modalità a contrasto elevato e con una proprietà <xref:System.Windows.Forms.PropertyGrid.PropertySort> impostata su <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> ora visualizzeranno lo sfondo delle intestazioni di categoria usando un colore a contrasto elevato.
- I controlli <xref:System.Windows.Forms.PropertyGrid> riconoscono meglio la differenza tra gli elementi della barra degli strumenti con stato attivo e gli elementi della barra degli strumenti che indicano il valore corrente della proprietà <xref:System.Windows.Forms.PropertyGrid.PropertySort>. Questa correzione prevede una modifica del contrasto elevato e una modifica per gli scenari non a contrasto elevato.
- Gli elementi della barra degli strumenti del controllo <xref:System.Windows.Forms.PropertyGrid> che indica il valore corrente della proprietà <xref:System.Windows.Forms.PropertyGrid.PropertySort> supportano la classe <xref:System.Windows.Automation.TogglePattern>.
- Supporto migliorato dell'Assistente vocale per distinguere l'allineamento selezionato in Selezione allineamento.
- Quando un controllo <xref:System.Windows.Forms.PropertyGrid> vuoto viene visualizzato in un form, ora riceve lo stato attivo nel punto in cui in precedenza non lo avrebbe ricevuto.

**Uso di colori definiti dal sistema operativo nei temi a contrasto elevato**

- I controlli <xref:System.Windows.Forms.Button> e <xref:System.Windows.Forms.CheckBox> con la proprietà <xref:System.Windows.Forms.ButtonBase.FlatStyle> impostata sullo stile predefinito <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType> ora usano i colori definiti dal sistema operativo nel tema a contrasto elevato quando selezionato. In precedenza, i colori di sfondo e testo non erano in contrasto e risultavano di difficile lettura.
- I controlli <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, <xref:System.Windows.Forms.Label>, <xref:System.Windows.Forms.LinkLabel>, e <xref:System.Windows.Forms.GroupBox> con la proprietà <xref:System.Windows.Forms.Control.Enabled> impostata su **false**, usavano un colore sfumato per eseguire il rendering del testo nei temi a contrasto elevato. In questo modo il contrasto con lo sfondo risultava minimo. Ora questi controlli usano il colore &quot;Testo disattivato&quot; definito dal sistema operativo. Questa correzione si applica ai controlli con la proprietà `FlatStyle` impostata su un valore diverso da <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType>. Il rendering di questi ultimi controlli viene eseguito dal sistema operativo.
- <xref:System.Windows.Forms.DataGridView> ora esegue il rendering di un rettangolo visibile intorno al contenuto della cella che ha lo stato attivo corrente. In precedenza, non era visibile in alcuni temi a contrasto elevato.
- I controlli <xref:System.Windows.Forms.ToolStripMenuItem> con la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Enabled> impostata su **False** ora usano il colore &quot;Testo disattivato&quot; definito dal sistema operativo.
- I controlli <xref:System.Windows.Forms.ToolStripMenuItem> con la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Checked> impostata su **True** ora eseguono il rendering del segno di spunta associato usando un colore di sistema di contrasto.  In precedenza, il colore del segno di spunta non era sufficientemente in contrasto e non era visibile in temi a contrasto elevato.
NOTA: in Windows 10 sono stati modificati i valori per alcuni colori di sistema a contrasto elevato. Il framework di Windows Form Framework si basa sul framework Win32. Per un'esperienza ottimale, eseguire nella versione più recente di Windows e acconsentire esplicitamente alle modifiche del sistema operativo più recenti aggiungendo un file app. manifest in un'applicazione di test e annullando il commento del codice seguente:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

**Navigazione tramite tastiera migliorata**

- Quando un controllo <xref:System.Windows.Forms.ComboBox> ha la proprietà <xref:System.Windows.Forms.ComboBox.DropDownStyle> impostata su <xref:System.Windows.Forms.ComboBoxStyle.DropDownList?displayProperty=nameWithType> ed è il primo controllo nell'ordine di tabulazione nel form, ora viene visualizzato un rettangolo di selezione quando il form padre viene aperto tramite la tastiera. Prima di questa modifica, lo stato attivo della tastiera era su questo controllo, ma non veniva eseguito il rendering di un indicatore dello stato attivo.

**Supporto migliorato di Assistente vocale**

- Il controllo <xref:System.Windows.Forms.MonthCalendar> ha aggiunto supporto per tipi di assistive technology che facilitano l'accesso al controllo. È inclusa la possibilità per Assistente vocale di leggere il valore del controllo, quando in precedenza non era possibile.

- Il controllo <xref:System.Windows.Forms.CheckedListBox> ora invia una notifica all'Assistente vocale quando una proprietà <xref:System.Windows.Forms.CheckBox.CheckState?displayProperty=nameWithType> è stata modificata. In precedenza, l'Assistente vocale non riceveva notifiche e di conseguenza gli utenti non venivano informati dell'aggiornamento della proprietà <xref:System.Windows.Forms.CheckBox.CheckState>.
- Il controllo <xref:System.Windows.Forms.LinkLabel> ha modificato il modo di notificare all'Assistente vocale il testo del controllo. In precedenza, l'Assistente vocale annunciava il testo due volte e leggeva i simboli &quot;&amp;&quot; come testo reale anche se non erano visibili a un utente. Il testo duplicato è stato rimosso dagli annunci dell'Assistente vocale, così come i simboli &quot;&amp;&quot; non necessari.
- I tipi di controllo <xref:System.Windows.Forms.DataGridViewCell> ora segnalano correttamente lo stato di sola lettura all'Assistente vocale e ad altri tipi di assistive technology.
- L'Assistente vocale ora legge il menu di sistema delle finestre figlio nelle applicazioni [Multiple-Document Interface]~/docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md).
- Assistente vocale ora può leggere i controlli <xref:System.Windows.Forms.ToolStripMenuItem>con una proprietà <xref:System.Windows.Forms.ToolStripItem.Enabled?displayProperty=nameWithType>impostata su **False**. In precedenza, l'Assistente vocale non poteva accedere alle voci di menu disabilitate per leggerne il contenuto.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Principale       |
| Version | 4.8         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.ToolStripDropDownButton.CreateAccessibilityInstance?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownAccessibleObject.Name?displayProperty=nameWithType>
- [MonthCalendar.AccessibilityObject](xref:System.Windows.Forms.Control.AccessibilityObject)
