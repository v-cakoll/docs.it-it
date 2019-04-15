---
ms.openlocfilehash: e73fe48467ede501bae0ddd9362d9d55b3ca998b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234077"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>Azioni upbutton e downbutton del dominio di Windows Forms ora sincronizzate

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.1 e versioni precedenti, l'azione <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> del controllo <xref:System.Windows.Forms.DomainUpDown> viene ignorata se è presente testo del controllo e lo sviluppatore deve usare l'azione <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> sul controllo prima di usare l'azione <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. A partire da .NET Framework 4.7.2 entrambe le azioni <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> e <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> funzionano in modo indipendente in questo scenario e rimangono sincronizzate.|
|Suggerimento|Perché un'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.7.2 o versione successiva. L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:<ul><li>Viene ricompilata per usare .NET Framework 4.7.2. Questa modifica è abilitata per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.</li><li>Rifiuta esplicitamente il comportamento di scorrimento legacy aggiungendo l'[opzione AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config e impostandola su <code>false</code>, come illustrato nell'esempio seguente.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType></li><li><xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType></li></ul>|
