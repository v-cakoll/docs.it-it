---
ms.openlocfilehash: 9ec5fa379556dedeaa7a35e34f004340ab47a39c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804478"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>Modifica della chiamata di CreateDefaultAuthorizationContext con un argomento Null

|   |   |
|---|---|
|Dettagli|L'implementazione di <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=name> restituito da una chiamata a <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=name> con un argomento authorizationPolicies Null è cambiata in .NET Framework 4.6.|
|Suggerimento|In rari casi, le app WCF che usano l'autenticazione personalizzata possono riscontrare differenze di comportamento. In questi casi è possibile ripristinare il comportamento precedente in due modi diversi:<ol><li>Ricompilare l'app per destinarla a una versione precedente rispetto a .NET Framework 4.6. Per i servizi ospitati in IIS, usare l'elemento &lt;httpRuntime targetFramework=&quot;x.x&quot; /&gt; per destinare l'app a una versione precedente di .NET Framework.</li><li>Aggiungere la riga seguente alla sezione <code>&lt;appSettings&gt;</code> del file app.config: <code>&lt;add key=&quot;appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext&quot; value=&quot;true&quot; /&gt;</code></li></ol>|
|Scope|Minorenne|
|Versione|4.6|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType></li></ul>|
