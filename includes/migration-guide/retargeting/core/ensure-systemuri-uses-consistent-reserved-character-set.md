---
ms.openlocfilehash: 2ec5224b1ab16c05f6f942f6084f1ab105b71b0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59233942"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>Verificare che System.Uri usi un set di caratteri riservati coerente

|   |   |
|---|---|
|Dettagli|In <xref:System.Uri?displayProperty=fullName>, alcuni caratteri codificati con percentuali che in determinati casi apparivano come non codificati ora sono codificati in modo uniforme. Questo si verifica in tutte le proprietà e i metodi che accedono ai componenti path, query, fragment o userinfo dell'URI. Il comportamento viene modificato solo quando entrambe le condizioni seguenti sono vere:<ul><li>L'URI contiene il formato codificato di uno qualsiasi dei caratteri riservati seguenti: <code>:</code>, <code>'</code>, <code>(</code>, <code>)</code>, <code>!</code> o <code>*</code>.</li><li>L'URI contiene un carattere non riservato Unicode o codificato. Se entrambe le precedenti condizioni sono vere, i caratteri riservati codificati restano codificati. Nelle versioni di .NET Framework precedenti i caratteri vengono decodificati.</li></ul>|
|Suggerimento|Per le applicazioni destinate a versioni di .NET Framework a partire dalla 4.7.2, il nuovo comportamento di rimozione della codifica è abilitato per impostazione predefinita. Se questa modifica non è opportuna, è possibile disabilitarla aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'app:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Per le applicazioni che sono destinate a versioni di .NET Framework precedenti ma vengono eseguite con versioni a partire da .NET Framework 4.7.2, il nuovo comportamento di rimozione della codifica è disabilitato per impostazione predefinita. È possibile abilitarlo aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'app:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
