---
ms.openlocfilehash: 53ded5ae6e5a025fc7992da099c3481587bb6f31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614901"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a>Rilascio di risorse tipo di carattere da parte del metodo PrivateFontCollection.AddFontFile

#### <a name="details"></a>Dettagli

In .NET Framework 4.7.1 e versioni precedenti, la classe <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> non rilascia le risorse tipo di carattere GDI+ dopo l'eliminazione di <xref:System.Drawing.Text.PrivateFontCollection> per gli oggetti <xref:System.Drawing.Font> che vengono aggiunti a questa raccolta tramite il metodo <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)>. In .NET Framework 4.7.2 e versioni successive, <xref:System.Drawing.Text.FontCollection.Dispose%2A> rilascia i tipi di carattere GDI+ aggiunti alla raccolta come file.

#### <a name="suggestion"></a>Suggerimento

**Come acconsentire esplicitamente o escludere queste modifiche** Affinché un'applicazione tragga vantaggio da queste modifiche, è necessario che venga eseguita nel .NET Framework 4.7.2 o versione successiva. L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:

- Viene ricompilata in modo da essere destinata a .NET Framework 4.7.2. Questa modifica è abilitata per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.
- È destinata a .NET Framework 4.7.1 o versione precedente e rifiuta esplicitamente i comportamenti di accessibilità legacy aggiungendo l'[opzione AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

Le applicazioni destinate a .NET Framework 4.7.2 o versione successiva che vogliono mantenere il comportamento legacy possono acconsentire esplicitamente a non rilasciare risorse tipo di carattere impostando in modo esplicito questa opzione AppContext su `true`.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
