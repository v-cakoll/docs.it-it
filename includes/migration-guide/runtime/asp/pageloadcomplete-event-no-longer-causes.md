---
ms.openlocfilehash: 39d609c955596354d1af28b4ed19d367dab0462b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620155"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>L'evento Page.LoadComplete non causa più la chiamata al data binding da parte del controllo System.Web.UI.WebControls.EntityDataSource

#### <a name="details"></a>Dettagli

L'evento <xref:System.Web.UI.Page.LoadComplete> non determina più la chiamata all'associazione dati da parte del controllo <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> per modifiche ai parametri di creazione/aggiornamento/eliminazione. Questa modifica determina l'eliminazione di un accesso estraneo al database, impedisce la reimpostazione dei valori dei controlli e genera un comportamento coerente con altri controlli di dati, quali <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> e <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>. Questa modifica determina un comportamento diverso nel caso improbabile in cui le applicazioni si affidino al richiamo dell'associazione dati nell'evento <xref:System.Web.UI.Page.LoadComplete>.

#### <a name="suggestion"></a>Suggerimento

Se il data binding è necessario, richiamare manualmente databind in un evento in una posizione precedente nel postback.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime|
