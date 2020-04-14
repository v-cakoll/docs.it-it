---
ms.openlocfilehash: c10d617e07ca2fa0239298d449d93cf833b83fce
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275468"
---
### <a name="calls-to-claimsidentity-constructors"></a>Chiamate dei costruttori ClaimsIdentity

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6.2 è stata introdotta una modifica al modo in cui i costruttori <xref:System.Security.Claims.ClaimsIdentity> con un parametro <xref:System.Security.Principal.IIdentity?displayProperty=name> impostano la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name>. Se l'argomento <xref:System.Security.Principal.IIdentity?displayProperty=name> è un oggetto <xref:System.Security.Claims.ClaimsIdentity> e la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> di tale oggetto <xref:System.Security.Claims.ClaimsIdentity> non è <code>null</code>, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> viene allegata usando il metodo <xref:System.Security.Claims.ClaimsIdentity.Clone>. In .NET Framework 4.6.1 e versioni precedenti, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> viene associata come riferimento esistente. In seguito a questa modifica, a partire da .NET Framework 4.6.2, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> del nuovo oggetto <xref:System.Security.Claims.ClaimsIdentity> non è uguale alla proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> dell'argomento <xref:System.Security.Principal.IIdentity?displayProperty=name> del costruttore. In .NET Framework 4.6.1 e versioni precedenti è uguale.|
|Suggerimento|Se questo comportamento è inaccettabile, è possibile ripristinare il comportamento precedente impostando il commutatore <code>Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity</code> nel file di configurazione dell'applicazione su <code>true</code>. A questo scopo è necessario aggiungere il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file web.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Microsoft Edge|
|Versione|4.6.2|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)></li><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})></li><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)></li></ul>|
