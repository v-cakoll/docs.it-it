---
ms.openlocfilehash: 7002c74594993ac6bf28643ef3271da356190c66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621964"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ValidationContext.MemberName di ASP.NET non è NULL quando si usa l'oggetto DataAnnotations.ValidationAttribute personalizzato

#### <a name="details"></a>Dettagli

In .NET Framework 4.7.2 e versioni precedenti, quando si usa un oggetto <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> personalizzato, la proprietà <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> restituisce `null`. In .NET Framework 4,8 versione precedente all'aggiornamento del 2019 ottobre, viene restituito il nome del membro. A partire da [.NET Framework ottobre 2019, anteprima del rollup qualitativo](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) per .NET Framework 4,8, restituisce per `null` impostazione predefinita, ma è possibile acconsentire esplicitamente a restituire il nome del membro.

#### <a name="suggestion"></a>Suggerimento

Aggiungere l'impostazione seguente al file di *web.config* per la proprietà in modo che restituisca il nome del membro nell' [anteprima .NET Framework ottobre 2019 dell'anteprima del rollup qualitativo](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) per .NET Framework 4,8 e versioni successive:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>In .NET Framework 4,8 versione precedente all'aggiornamento di ottobre 2019, l'aggiunta di questo al file *web.config* ripristina il comportamento precedente e la proprietà restituisce `null` .

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Sconosciuto|
|Version|4.8|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
