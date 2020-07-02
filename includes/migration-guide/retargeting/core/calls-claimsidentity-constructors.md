---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614432"
---
### <a name="calls-to-claimsidentity-constructors"></a>Chiamate dei costruttori ClaimsIdentity

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6.2 è stata introdotta una modifica al modo in cui i costruttori <xref:System.Security.Claims.ClaimsIdentity> con un parametro <xref:System.Security.Principal.IIdentity?displayProperty=fullName> impostano la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>. Se l'argomento <xref:System.Security.Principal.IIdentity?displayProperty=fullName> è un oggetto <xref:System.Security.Claims.ClaimsIdentity> e la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> di tale oggetto <xref:System.Security.Claims.ClaimsIdentity> non è `null`, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> viene allegata usando il metodo <xref:System.Security.Claims.ClaimsIdentity.Clone>. In .NET Framework 4.6.1 e versioni precedenti, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> viene associata come riferimento esistente. In seguito a questa modifica, a partire da .NET Framework 4.6.2, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> del nuovo oggetto <xref:System.Security.Claims.ClaimsIdentity> non è uguale alla proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> dell'argomento <xref:System.Security.Principal.IIdentity?displayProperty=fullName> del costruttore. In .NET Framework 4.6.1 e versioni precedenti è uguale.

#### <a name="suggestion"></a>Suggerimento

Se questo comportamento è inaccettabile, è possibile ripristinare il comportamento precedente impostando il commutatore `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` nel file di configurazione dell'applicazione su `true`. A questo scopo è necessario aggiungere il codice seguente alla sezione `<runtime>` del file web.config:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
