---
ms.openlocfilehash: 39d609c955596354d1af28b4ed19d367dab0462b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620155"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a><span data-ttu-id="c28e7-101">L'evento Page.LoadComplete non causa più la chiamata al data binding da parte del controllo System.Web.UI.WebControls.EntityDataSource</span><span class="sxs-lookup"><span data-stu-id="c28e7-101">Page.LoadComplete event no longer causes System.Web.UI.WebControls.EntityDataSource control to invoke data binding</span></span>

#### <a name="details"></a><span data-ttu-id="c28e7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c28e7-102">Details</span></span>

<span data-ttu-id="c28e7-103">L'evento <xref:System.Web.UI.Page.LoadComplete> non determina più la chiamata all'associazione dati da parte del controllo <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> per modifiche ai parametri di creazione/aggiornamento/eliminazione.</span><span class="sxs-lookup"><span data-stu-id="c28e7-103">The <xref:System.Web.UI.Page.LoadComplete> event no longer causes the <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> control to invoke data binding for changes to create/update/delete parameters.</span></span> <span data-ttu-id="c28e7-104">Questa modifica determina l'eliminazione di un accesso estraneo al database, impedisce la reimpostazione dei valori dei controlli e genera un comportamento coerente con altri controlli di dati, quali <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> e <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="c28e7-104">This change eliminates an extraneous trip to the database, prevents the values of controls from being reset, and produces behavior that is consistent with other data controls, such as <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> and <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span></span> <span data-ttu-id="c28e7-105">Questa modifica determina un comportamento diverso nel caso improbabile in cui le applicazioni si affidino al richiamo dell'associazione dati nell'evento <xref:System.Web.UI.Page.LoadComplete>.</span><span class="sxs-lookup"><span data-stu-id="c28e7-105">This change produces different behavior in the unlikely event that applications rely on invoking data binding in the <xref:System.Web.UI.Page.LoadComplete> event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c28e7-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c28e7-106">Suggestion</span></span>

<span data-ttu-id="c28e7-107">Se il data binding è necessario, richiamare manualmente databind in un evento in una posizione precedente nel postback.</span><span class="sxs-lookup"><span data-stu-id="c28e7-107">If there is a need for databinding, manually invoke databind in an event that is earlier in the post-back.</span></span>

| <span data-ttu-id="c28e7-108">Nome</span><span class="sxs-lookup"><span data-stu-id="c28e7-108">Name</span></span>    | <span data-ttu-id="c28e7-109">Valore</span><span class="sxs-lookup"><span data-stu-id="c28e7-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c28e7-110">Scope</span><span class="sxs-lookup"><span data-stu-id="c28e7-110">Scope</span></span>   |<span data-ttu-id="c28e7-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c28e7-111">Edge</span></span>|
|<span data-ttu-id="c28e7-112">Version</span><span class="sxs-lookup"><span data-stu-id="c28e7-112">Version</span></span>|<span data-ttu-id="c28e7-113">4.5</span><span class="sxs-lookup"><span data-stu-id="c28e7-113">4.5</span></span>|
|<span data-ttu-id="c28e7-114">Type</span><span class="sxs-lookup"><span data-stu-id="c28e7-114">Type</span></span>|<span data-ttu-id="c28e7-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="c28e7-115">Runtime</span></span>|
