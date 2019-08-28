---
ms.openlocfilehash: 3b94c88809513e31a5f226bcfce39abbfa4de378
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70017372"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ValidationContext.MemberName di ASP.NET non è NULL quando si usa l'oggetto DataAnnotations.ValidationAttribute personalizzato

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.2 e versioni precedenti, quando si usa un oggetto <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> personalizzato, la proprietà <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> restituisce <code>null</code>.  In .NET Framework 4.8 restituisce il nome del membro.|
|Suggerimento|Per ripristinare il comportamento precedente, aggiungere l'impostazione seguente al file di configurazione dell'app:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Questo comportamento verrà modificato in una prossima Service Release, quando sarà necessario acconsentire esplicitamente al nuovo comportamento. La proprietà restituirà un valore non Null per un `ValidationAttribute` personalizzato se l'opzione `aspnet:GetValidationMemberName` è impostata su `true`.|
|Ambito|Sconosciuto|
|Versione|4.8|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
