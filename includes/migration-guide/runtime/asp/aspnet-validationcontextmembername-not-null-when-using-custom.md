---
ms.openlocfilehash: c0be08023f80bf0f96cc08f34b9ea8c5a73839e3
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77466027"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ValidationContext.MemberName di ASP.NET non è NULL quando si usa l'oggetto DataAnnotations.ValidationAttribute personalizzato

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.2 e versioni precedenti, quando si usa un oggetto <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> personalizzato, la proprietà <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> restituisce `null`. In .NET Framework 4,8 versione precedente all'aggiornamento del 2019 ottobre, viene restituito il nome del membro. A partire da [.NET Framework ottobre 2019, anteprima del rollup qualitativo](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) per .NET Framework 4,8, restituisce `null` per impostazione predefinita, ma è possibile acconsentire esplicitamente a restituire il nome del membro. |
|Suggerimento|Aggiungere l'impostazione seguente al file *Web. config* per la proprietà per restituire il nome del membro in [.NET Framework anteprima del 2019 ottobre del rollup qualitativo](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) per .NET Framework 4,8 e versioni successive:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>In .NET Framework 4,8 versione precedente all'aggiornamento di ottobre 2019, l'aggiunta di questo al file *Web. config* consente di ripristinare il comportamento precedente e la proprietà restituisce `null`.|
|Ambito|Sconosciuto|
|Versione|4.8|
|Type|Tipo|
|API interessate|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
