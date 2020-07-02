---
ms.openlocfilehash: 47d3829748deef2c7c3610816b8941bf88da7ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614924"
---
### <a name="accessibility-improvements-in-wpf"></a>Miglioramenti di accessibilità in WPF

#### <a name="details"></a>Dettagli

**Miglioramenti del contrasto elevato**
<ul><li>Lo stato attivo per il controllo <xref:System.Windows.Controls.Expander> ora è visibile. Nelle versioni precedenti di .NET Framework, non accadeva così.
-Il testo in <xref:System.Windows.Controls.CheckBox> e i <xref:System.Windows.Controls.RadioButton> controlli quando sono selezionati sono ora più semplici da visualizzare rispetto alle versioni precedenti del .NET Framework.
-Il bordo di un oggetto disattivato <xref:System.Windows.Controls.ComboBox> è ora lo stesso colore del testo disabilitato. Nelle versioni precedenti di .NET Framework, non accadeva così.
-I pulsanti disabilitati e con stato attivo ora usano il colore del tema corretto. Nelle versioni precedenti di .NET Framework, non lo usavano.
-Il pulsante a discesa è ora visibile quando <xref:System.Windows.Controls.ComboBox> lo stile di un controllo è impostato su <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType> , nelle versioni precedenti del .NET Framework.
-La freccia dell'indicatore di ordinamento in un <xref:System.Windows.Controls.DataGrid> controllo Usa ora i colori del tema. Nelle versioni precedenti di .NET Framework, non accadeva così.
-Lo stile predefinito del collegamento ipertestuale viene ora modificato sul colore del tema corretto al passaggio del mouse. Nelle versioni precedenti di .NET Framework, non accadeva così.
-Lo stato attivo della tastiera sui pulsanti di opzione è ora visibile. Nelle versioni precedenti di .NET Framework, non accadeva così.
-La <xref:System.Windows.Controls.DataGrid> colonna CheckBox del controllo Usa ora i colori previsti per il feedback dello stato attivo della tastiera. Nelle versioni precedenti di .NET Framework, non accadeva così.
-gli oggetti visivi dello stato attivo della tastiera sono ora visibili nei <xref:System.Windows.Controls.ComboBox> <xref:System.Windows.Controls.ListBox> controlli e. Nelle versioni precedenti di .NET Framework, non accadeva così.</p>
**Miglioramenti dell'interazione con la lettura schermo**
<ul><li>I controlli <xref:System.Windows.Controls.Expander> ora sono correttamente annunciati come gruppi (di espansione/compresione) dalle utilità per la lettura dello schermo.
I controlli - <xref:System.Windows.Controls.DataGridCell> ora sono correttamente annunciati come cella della griglia dati (localizzata) dalle utilità per la lettura dello schermo.
-Le utilità per la lettura dello schermo ora annunciano il nome di un oggetto modificabile <xref:System.Windows.Controls.ComboBox> .
I controlli - <xref:System.Windows.Controls.PasswordBox> non sono più annunciati come &quot;nessun elemento visualizzato&quot; dalle utilità per la lettura dello schermo.</p>
**Supporto di LiveRegion** Le utilità per la lettura dello schermo, ad esempio Assistente vocale, consentono agli utenti di conoscere il contenuto dell'interfaccia utente di un'applicazione, in genere descrivendo qualcosa sull'interfaccia utente attualmente concentrata, perché questo è probabilmente l'elemento di maggiore interesse per l'utente. Se tuttavia un elemento qualsiasi dell'interfaccia utente viene modificato sullo schermo e non ha lo stato attivo, l'utente potrebbe non riceverne notifica e perdere informazioni importanti. Le aree dinamiche servono a risolvere questo problema. Uno sviluppatore può usarle per informare l'utilità per la lettura dello schermo o qualsiasi altro client [UIAutomation](~/docs/framework/ui-automation/ui-automation-overview.md) di un'importante modifica apportata a un elemento dell'interfaccia utente. L'utilità per la lettura dello schermo può quindi decidere come e quando informare l'utente di questa modifica. La proprietà LiveSetting consente anche all'utilità per la lettura dello schermo di sapere se è importante informare l'utente della modifica apportata all'interfaccia utente.

#### <a name="suggestion"></a>Suggerimento

**Come acconsentire esplicitamente o escludere queste modifiche** Per consentire all'applicazione di trarre vantaggio da queste modifiche, è necessario eseguirla nel .NET Framework 4.7.1 o versione successiva. L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:

- Usare .NET Framework 4.7.1. Questo è l'approccio consigliato. Queste modifiche di accessibilità sono abilitate per impostazione predefinita nelle applicazioni WPF che usano .NET Framework 4.7.1 o versione successiva.
- I comportamenti di accessibilità legacy vengono rifiutati esplicitamente aggiungendo l'[opzione di AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Le applicazioni che usano .NET Framework 4.7.1 o versione successiva e che vogliono mantenere il comportamento di accessibilità legacy possono scegliere di usare le funzionalità di accessibilità legacy impostando in modo esplicito questa opzione di AppContext su `true`.
Per una panoramica dell'automazione interfaccia utente, vedere [Panoramica di automazione interfaccia utente](~/docs/framework/ui-automation/ui-automation-overview.md).

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Principale       |
| Version | 4.7.1       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting(System.Windows.DependencyObject,System.Windows.Automation.AutomationLiveSetting)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting(System.Windows.DependencyObject)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore?displayProperty=nameWithType>
