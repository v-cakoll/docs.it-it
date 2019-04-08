---
ms.openlocfilehash: 948c83f49b703194ccfe932e53751e0bb2dde37c
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760807"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>La proprietà ContextMenuStrip.SourceControl contiene un controllo valido in caso di ToolStripMenuItems annidati

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.1 e versioni precedenti, la proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> restituisce erroneamente Null quando l'utente apre il menu da controlli <xref:System.Windows.Forms.ToolStripMenuItem> annidati. In .NET Framework 4.7.2 e versioni successive, la proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> è sempre impostata sul controllo del codice sorgente effettivo.|
|Suggerimento|<strong>Come accettare o rifiutare queste modifiche</strong>Affinché un'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.7.2 o versione successiva. L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:<ul><li>È destinata a .NET Framework 4.7.2. Questa modifica è abilitata per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.</li><li>È destinata a .NET Framework 4.7.1 o versione precedente e rifiuta esplicitamente i comportamenti di accessibilità legacy aggiungendo l'[opzione AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config e impostandola su <code>false</code>, come illustrato nell'esempio seguente.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Le applicazioni destinate a .NET Framework 4.7.2 o versione successiva e che vogliono mantenere il comportamento legacy possono acconsentire esplicitamente all'uso del valore del controllo del codice sorgente legacy impostando in modo esplicito questa opzione AppContext su <code>true</code>.|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType></li></ul>|

