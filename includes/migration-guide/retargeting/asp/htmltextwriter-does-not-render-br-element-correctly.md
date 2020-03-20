---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804413"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a>HtmlTextWriter non esegue correttamente il rendering dell'elemento `<br/>`

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6, la chiamata di <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> e <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento <code>&lt;BR /&gt;</code> inserirà correttamente solo un <code>&lt;BR /&gt;</code> (invece di due)|
|Suggerimento|Se un'app dipende dal tag <code>&lt;BR /&gt;</code> aggiuntivo, il metodo <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> deve essere chiamato una seconda volta. Si noti che questa modifica di comportamento influisce solo sulle app destinate a .NET Framework 4.6 o versioni successive, quindi è possibile in alternativa selezionare una versione precedente di .NET Framework come destinazione per ottenere il comportamento precedente.|
|Scope|Microsoft Edge|
|Versione|4.6|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|
