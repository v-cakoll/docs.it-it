---
ms.openlocfilehash: d78d083b16ac034c6c393dbc0f6094ee4c6c63c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622363"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="dc0f8-101">DataGridCellsPanel.BringIndexIntoView genera ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="dc0f8-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

#### <a name="details"></a><span data-ttu-id="dc0f8-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dc0f8-102">Details</span></span>

<span data-ttu-id="dc0f8-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> funziona in modo asincrono quando è abilitata la virtualizzazione delle colonne la cui larghezza tuttavia non è stata ancora determinata.</span><span class="sxs-lookup"><span data-stu-id="dc0f8-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="dc0f8-104">Se le colonne vengono rimosse prima dell'operazione asincrona, può verificarsi un evento <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="dc0f8-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> can occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dc0f8-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="dc0f8-105">Suggestion</span></span>

<span data-ttu-id="dc0f8-106">Una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc0f8-106">Any one of the following:</span></span><ol><li><span data-ttu-id="dc0f8-107">Effettuare l'aggiornamento a .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="dc0f8-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="dc0f8-108">Installare la patch più recente per la manutenzione di .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="dc0f8-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="dc0f8-109">Evitare di rimuovere colonne fino al completamento della risposta asincrona a <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</span><span class="sxs-lookup"><span data-stu-id="dc0f8-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>

| <span data-ttu-id="dc0f8-110">Nome</span><span class="sxs-lookup"><span data-stu-id="dc0f8-110">Name</span></span>    | <span data-ttu-id="dc0f8-111">Valore</span><span class="sxs-lookup"><span data-stu-id="dc0f8-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dc0f8-112">Scope</span><span class="sxs-lookup"><span data-stu-id="dc0f8-112">Scope</span></span>   |<span data-ttu-id="dc0f8-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dc0f8-113">Edge</span></span>|
|<span data-ttu-id="dc0f8-114">Version</span><span class="sxs-lookup"><span data-stu-id="dc0f8-114">Version</span></span>|<span data-ttu-id="dc0f8-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="dc0f8-115">4.6.2</span></span>|
|<span data-ttu-id="dc0f8-116">Type</span><span class="sxs-lookup"><span data-stu-id="dc0f8-116">Type</span></span>|<span data-ttu-id="dc0f8-117">Runtime</span><span class="sxs-lookup"><span data-stu-id="dc0f8-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dc0f8-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="dc0f8-118">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
