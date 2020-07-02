---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615649"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a>HtmlTextWriter non esegue correttamente il rendering dell'elemento `<br/>`

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6, la chiamata di <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> e <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento `<BR />` inserirà correttamente solo un `<BR />` (invece di due)

#### <a name="suggestion"></a>Suggerimento

Se un'app dipende dal tag `<BR />` aggiuntivo, il metodo <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> deve essere chiamato una seconda volta. Si noti che questa modifica di comportamento influisce solo sulle app destinate a .NET Framework 4.6 o versioni successive, quindi è possibile in alternativa selezionare una versione precedente di .NET Framework come destinazione per ottenere il comportamento precedente.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>
