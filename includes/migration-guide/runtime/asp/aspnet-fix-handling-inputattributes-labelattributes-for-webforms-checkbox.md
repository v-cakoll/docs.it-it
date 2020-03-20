---
ms.openlocfilehash: ea0e1583cd611a624cf2d2edf9defb2294eb89d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802659"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>Gestione delle correzioni ASP.NET di InputAttributes e LabelAttributes per il controllo CheckBox di WebForms

|   |   |
|---|---|
|Dettagli|Per le applicazioni destinate a .NET Framework 4.7.2 e versioni precedenti, le proprietà <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> e <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> aggiunte a livello di codice a un controllo <xref:System.Web.UI.WebControls.CheckBox> di WebForms vengono perse dopo il postback. Per le applicazioni destinate a .NET Framework 4.8 o versioni successive, vengono mantenute dopo il postback.|
|Suggerimento|Per il comportamento corretto per il ripristino degli attributi durante il postback, impostare <code>targetFrameworkVersion</code> sulla versione 4.8 o successiva. Ad esempio:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Se viene impostata una versione precedente o se non viene impostata alcuna versione, viene riprodotto il comportamento errato.|
|Scope|Unknown|
|Versione|4.8|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
