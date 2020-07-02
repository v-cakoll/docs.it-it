---
ms.openlocfilehash: 3b329bf5ba2af4d3ab9c3e203e99daba8ca0d0c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620140"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a>GridViews con AllowCustomPaging impostato su true può generare l'evento PageIndexChanging quando si esce dalla pagina finale della visualizzazione

#### <a name="details"></a>Dettagli

A causa di un bug in .NET Framework 4.5, <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> a volte non viene generato per le classi <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> che hanno abilitato la proprietà <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework. Come soluzione alternativa, l'app può eseguire un'operazione BindGrid esplicita su qualsiasi <code>Page_Load</code> che soddisfi queste condizioni (la classe <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> è nell'ultima pagina e la proprietà Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> è diversa da <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>). Oppure è possibile modificare l'app in modo da consentire il paging (anziché il paging personalizzato), poiché in questo scenario il problema non si verifica.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
