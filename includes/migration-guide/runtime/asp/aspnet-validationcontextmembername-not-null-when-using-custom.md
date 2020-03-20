---
ms.openlocfilehash: c0be08023f80bf0f96cc08f34b9ea8c5a73839e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77466027"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ValidationContext.MemberName di ASP.NET non è NULL quando si usa l'oggetto DataAnnotations.ValidationAttribute personalizzato

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.2 e versioni precedenti, quando si usa un oggetto <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> personalizzato, la proprietà <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> restituisce `null`. In .NET Framework 4.8 versione precedente all'aggiornamento di ottobre 2019, restituisce il nome del membro. A partire da [.NET Framework ottobre 2019 Anteprima del rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) `null` di qualità per .NET Framework 4.8, restituisce per impostazione predefinita, ma è possibile scegliere di restituire il nome del membro. |
|Suggerimento|Aggiungere l'impostazione seguente al file *web.config* per la proprietà per restituire il nome del membro in [.NET Framework ottobre 2019 Anteprima del rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) di qualità per.NET Framework 4.8 e versioni successive:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Nella versione di .NET Framework 4.8 precedente all'aggiornamento di ottobre 2019, l'aggiunta `null`al file *web.config* ripristina il comportamento precedente e la proprietà restituisce .|
|Scope|Unknown|
|Versione|4.8|
|Type|Runtime|
|API interessate|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
