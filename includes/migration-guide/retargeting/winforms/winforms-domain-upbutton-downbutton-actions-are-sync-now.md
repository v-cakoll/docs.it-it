---
ms.openlocfilehash: f75a652f15be6b0d184db20dc5cd8aafd80539fe
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614910"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>Azioni upbutton e downbutton del dominio di Windows Forms ora sincronizzate

#### <a name="details"></a>Dettagli

In .NET Framework 4.7.1 e versioni precedenti, l'azione <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> del controllo <xref:System.Windows.Forms.DomainUpDown> viene ignorata se è presente testo del controllo e lo sviluppatore deve usare l'azione <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> sul controllo prima di usare l'azione <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. A partire da .NET Framework 4.7.2 entrambe le azioni <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> e <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> funzionano in modo indipendente in questo scenario e rimangono sincronizzate.

#### <a name="suggestion"></a>Suggerimento

Perché un'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.7.2 o versione successiva. L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:

- Viene ricompilata in modo da essere destinata a .NET Framework 4.7.2. Questa modifica è abilitata per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.
- Rifiuta esplicitamente il comportamento di scorrimento legacy aggiungendo l'[opzione AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
