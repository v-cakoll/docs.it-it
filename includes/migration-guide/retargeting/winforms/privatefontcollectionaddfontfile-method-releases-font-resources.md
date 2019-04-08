---
ms.openlocfilehash: c923d9b341bbf0a21d73ac75cc6cb1a037f37826
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760808"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a>Rilascio di risorse tipo di carattere da parte del metodo PrivateFontCollection.AddFontFile

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.1 e versioni precedenti, la classe <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> non rilascia le risorse tipo di carattere GDI+ dopo l'eliminazione di <xref:System.Drawing.Text.PrivateFontCollection> per gli oggetti <xref:System.Drawing.Font> che vengono aggiunti a questa raccolta tramite il metodo <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)>. In .NET Framework 4.7.2 e versioni successive, <xref:System.Drawing.Text.FontCollection.Dispose%2A> rilascia i tipi di carattere GDI+ aggiunti alla raccolta come file.|
|Suggerimento|<strong>Come accettare o rifiutare queste modifiche</strong>Affinché un'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.7.2 o versione successiva. L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:<ul><li>Viene ricompilata per usare .NET Framework 4.7.2. Questa modifica è abilitata per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.</li><li>È destinata a .NET Framework 4.7.1 o versione precedente e rifiuta esplicitamente i comportamenti di accessibilità legacy aggiungendo l'[opzione AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config e impostandola su <code>false</code>, come illustrato nell'esempio seguente.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Le applicazioni destinate a .NET Framework 4.7.2 o versione successiva che vogliono mantenere il comportamento legacy possono acconsentire esplicitamente a non rilasciare risorse tipo di carattere impostando in modo esplicito questa opzione AppContext su <code>true</code>.|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType></li><li><xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType></li></ul>|

