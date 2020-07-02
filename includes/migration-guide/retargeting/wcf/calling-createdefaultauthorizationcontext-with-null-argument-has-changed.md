---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615708"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>Modifica della chiamata di CreateDefaultAuthorizationContext con un argomento Null

#### <a name="details"></a>Dettagli

L'implementazione di <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> restituito da una chiamata a <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> con un argomento authorizationPolicies Null è cambiata in .NET Framework 4.6.

#### <a name="suggestion"></a>Suggerimento

In rari casi, le app WCF che usano l'autenticazione personalizzata possono riscontrare differenze di comportamento. In questi casi è possibile ripristinare il comportamento precedente in due modi diversi:

- Ricompilare l'app per destinarla a una versione precedente rispetto a .NET Framework 4.6. Per i servizi ospitati in IIS, usare l'elemento `<httpRuntime targetFramework="x.x">` per destinare l'app a una versione precedente di .NET Framework.
- Aggiungere la riga seguente alla sezione `<appSettings>` del file app.config:

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
