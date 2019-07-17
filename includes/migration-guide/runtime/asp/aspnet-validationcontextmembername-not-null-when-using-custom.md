---
ms.openlocfilehash: df13f6938ebaf8e96bb2825c1495044621f1c31b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802720"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ValidationContext.MemberName di ASP.NET non è NULL quando si usa l'oggetto DataAnnotations.ValidationAttribute personalizzato

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.2 e versioni precedenti, quando si usa un oggetto <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> personalizzato, la proprietà <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> restituisce <code>null</code>.  In .NET Framework 4.8 restituisce il nome del membro.|
|Suggerimento|Il comportamento predefinito della proprietà <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> rimane invariato.  Per recuperare un valore valido dalla proprietà <code>ValidationContext.MemberName</code>, aggiungere l'impostazione seguente al file di configurazione dell'app:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Sconosciuto|
|Versione|4.8|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|

