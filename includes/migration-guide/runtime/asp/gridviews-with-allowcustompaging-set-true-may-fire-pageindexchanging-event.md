---
ms.openlocfilehash: c9c46793a0f66894649796d960547848ff5ebf8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858550"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a>GridViews con AllowCustomPaging impostato su true può generare l'evento PageIndexChanging quando si esce dalla pagina finale della visualizzazione

|   |   |
|---|---|
|Dettagli|A causa di un bug in .NET Framework 4.5, <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=name> a volte non viene generato per le classi <xref:System.Web.UI.WebControls.GridView?displayProperty=name> che hanno abilitato la proprietà <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=name>.|
|Suggerimento|Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework. Come soluzione alternativa, l'app può eseguire un'operazione BindGrid esplicita su qualsiasi <code>Page_Load</code> che soddisfi queste condizioni (la classe <xref:System.Web.UI.WebControls.GridView?displayProperty=name> è nell'ultima pagina e la proprietà Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name> è diversa da <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name>). Oppure è possibile modificare l'app in modo da consentire il paging (anziché il paging personalizzato), poiché in questo scenario il problema non si verifica.|
|Scope|Minorenne|
|Versione|4.5|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
