---
ms.openlocfilehash: 171b7a3a962f8259e64b88f1ae893e649b5f24bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621256"
---
### <a name="chained-popups-with-staysopenfalse"></a><span data-ttu-id="960b4-101">Popup concatenati con StaysOpen=False</span><span class="sxs-lookup"><span data-stu-id="960b4-101">Chained Popups with StaysOpen=False</span></span>

#### <a name="details"></a><span data-ttu-id="960b4-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="960b4-102">Details</span></span>

<span data-ttu-id="960b4-103">Un popup con StaysOpen=False deve chiudersi quando si fa clic all'esterno del popup.</span><span class="sxs-lookup"><span data-stu-id="960b4-103">A Popup with StaysOpen=False is supposed to close when you click outside the Popup.</span></span> <span data-ttu-id="960b4-104">Due o più popup concatenati, ad esempio un popup che ne contiene un altro, causavano molti problemi, tra cui:</span><span class="sxs-lookup"><span data-stu-id="960b4-104">When two or more such Popups are chained (i.e. one contains another), there were many problems, including:</span></span><ul><li><span data-ttu-id="960b4-105">Apertura di due livelli, clic all'esterno di P2, ma all'interno di P1.</span><span class="sxs-lookup"><span data-stu-id="960b4-105">Open two levels, click outside P2 but inside P1.</span></span>  <span data-ttu-id="960b4-106">Non accade nulla.</span><span class="sxs-lookup"><span data-stu-id="960b4-106">Nothing happens.</span></span></li><li><span data-ttu-id="960b4-107">Apertura di due livelli, clic all'esterno di P1.</span><span class="sxs-lookup"><span data-stu-id="960b4-107">Open two levels, click outside P1.</span></span>  <span data-ttu-id="960b4-108">Entrambi i popup vengono chiusi.</span><span class="sxs-lookup"><span data-stu-id="960b4-108">Both popups close.</span></span></li><li><span data-ttu-id="960b4-109">Apertura e chiusura di due livelli.</span><span class="sxs-lookup"><span data-stu-id="960b4-109">Open and close two levels.</span></span>  <span data-ttu-id="960b4-110">Riapertura di P2.</span><span class="sxs-lookup"><span data-stu-id="960b4-110">Then try to open P2 again.</span></span>  <span data-ttu-id="960b4-111">Non accade nulla.</span><span class="sxs-lookup"><span data-stu-id="960b4-111">Nothing happens.</span></span></li><li><span data-ttu-id="960b4-112">Apertura di tre livelli.</span><span class="sxs-lookup"><span data-stu-id="960b4-112">Try to open three levels.</span></span>  <span data-ttu-id="960b4-113">Non è possibile.</span><span class="sxs-lookup"><span data-stu-id="960b4-113">You can't.</span></span>  <span data-ttu-id="960b4-114">Non viene eseguita alcuna operazione o i primi due livelli si chiudono, a seconda della posizione in cui si fa clic. Questi casi (e altre varianti) funzionano ora come previsto.</span><span class="sxs-lookup"><span data-stu-id="960b4-114">(Either nothing happens or the first two levels close, depending on where you click.) These cases (and other variants) now work as expected.</span></span></li></ul>

| <span data-ttu-id="960b4-115">Nome</span><span class="sxs-lookup"><span data-stu-id="960b4-115">Name</span></span>    | <span data-ttu-id="960b4-116">Valore</span><span class="sxs-lookup"><span data-stu-id="960b4-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="960b4-117">Scope</span><span class="sxs-lookup"><span data-stu-id="960b4-117">Scope</span></span>   |<span data-ttu-id="960b4-118">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="960b4-118">Edge</span></span>|
|<span data-ttu-id="960b4-119">Version</span><span class="sxs-lookup"><span data-stu-id="960b4-119">Version</span></span>|<span data-ttu-id="960b4-120">4.7.1</span><span class="sxs-lookup"><span data-stu-id="960b4-120">4.7.1</span></span>|
|<span data-ttu-id="960b4-121">Type</span><span class="sxs-lookup"><span data-stu-id="960b4-121">Type</span></span>|<span data-ttu-id="960b4-122">Runtime</span><span class="sxs-lookup"><span data-stu-id="960b4-122">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="960b4-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="960b4-123">Affected APIs</span></span>

-<xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|
