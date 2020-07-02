---
ms.openlocfilehash: ae557ce57557d027dba35b7da213c08aee85f2c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621974"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>Gestione delle correzioni ASP.NET di InputAttributes e LabelAttributes per il controllo CheckBox di WebForms

#### <a name="details"></a>Dettagli

Per le applicazioni destinate a .NET Framework 4.7.2 e versioni precedenti, le proprietà <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> e <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> aggiunte a livello di codice a un controllo <xref:System.Web.UI.WebControls.CheckBox> di WebForms vengono perse dopo il postback. Per le applicazioni destinate a .NET Framework 4.8 o versioni successive, vengono mantenute dopo il postback.

#### <a name="suggestion"></a>Suggerimento

Per il comportamento corretto per il ripristino degli attributi durante il postback, impostare <code>targetFrameworkVersion</code> sulla versione 4.8 o successiva. Ad esempio:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Se viene impostata una versione precedente o se non viene impostata alcuna versione, viene riprodotto il comportamento errato.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Sconosciuto|
|Version|4.8|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
