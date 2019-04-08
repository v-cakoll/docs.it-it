---
ms.openlocfilehash: a29f0ca6d235250ac1f41e686178b2d6affcd8a0
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761128"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>Modifica della chiamata di CreateDefaultAuthorizationContext con un argomento Null

|   |   |
|---|---|
|Dettagli|L'implementazione di <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=name> restituito da una chiamata a <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=name> con un argomento authorizationPolicies Null è cambiata in .NET Framework 4.6.|
|Suggerimento|In rari casi, le app WCF che usano l'autenticazione personalizzata possono riscontrare differenze di comportamento. In questi casi è possibile ripristinare il comportamento precedente in due modi diversi:<ol><li>Ricompilare l'app per destinarla a una versione precedente rispetto a .NET Framework 4.6. Per i servizi ospitati in IIS, usare l'elemento &lt;httpRuntime targetFramework=&quot;x.x&quot; /&gt; per destinare l'app a una versione precedente di .NET Framework.</li><li>Aggiungere la riga seguente alla sezione <code>&lt;appSettings&gt;</code> del file app.config: <code>&lt;add key=&quot;appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext&quot; value=&quot;true&quot; /&gt;</code></li></ol>|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType></li></ul>|

