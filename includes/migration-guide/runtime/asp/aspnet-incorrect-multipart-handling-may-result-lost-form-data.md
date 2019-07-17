---
ms.openlocfilehash: 6a99ed916e4e86e85d7ebc2d6ea36a6372c00206
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802592"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a>La gestione multipart di ASP.NET non corretta può comportare la perdita di dati del modulo.

|   |   |
|---|---|
|Dettagli|Nelle applicazioni destinate a .NET Framework 4.7.2 e versioni precedenti, ASP.NET potrebbe analizzare erroneamente i valori limite multipart, causando la mancata disponibilità dei dati del modulo durante l'esecuzione della richiesta. Le applicazioni destinate a .NET Framework 4.8 o versioni successive analizzano i dati multipart correttamente. I dati del modulo sono quindi disponibili durante l'esecuzione della richiesta.|
|Suggerimento|Nelle applicazioni in esecuzione in .NET Framework a partire dalla versione 4.8 e destinate a .NET Framework 4.8 o versioni successive che usano l'elemento <code>targetFrameworkVersion</code>, il comportamento predefinito cambia al fine di eliminare i delimitatori. Se si usano versioni del framework precedenti o non si usa <code>targetFrameworkVersion</code>, è possibile che vengano restituiti dei delimitatori finali per alcuni valori.Questo comportamento può anche essere controllato esplicitamente con un elemento <code>appSetting</code>:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Sconosciuto|
|Versione|4.8|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Web.HttpRequest.Form?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.Files?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|

