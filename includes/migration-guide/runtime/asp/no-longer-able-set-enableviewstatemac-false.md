---
ms.openlocfilehash: cecb7b2abd4f57fdaacb0ea373cc19dc3cd9b24a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620167"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="15e25-101">Non è più possibile impostare EnableViewStateMac su false</span><span class="sxs-lookup"><span data-stu-id="15e25-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="15e25-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="15e25-102">Details</span></span>

<span data-ttu-id="15e25-103">ASP.NET non consente più agli sviluppatori di specificare <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="15e25-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="15e25-104">L'algoritmo Message Authentication Code (MAC) dello stato di visualizzazione viene ora applicato per tutte le richieste con stato di visualizzazione incorporato.</span><span class="sxs-lookup"><span data-stu-id="15e25-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="15e25-105">Riguarda solo le app che impostano in modo esplicito la proprietà EnableViewStateMac su <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="15e25-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="15e25-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="15e25-106">Suggestion</span></span>

<span data-ttu-id="15e25-107">EnableViewStateMac deve essere impostato su true e tutti gli errori MAC risultanti devono essere risolti (come illustrato in [questa guida](https://support.microsoft.com/kb/2915218), che contiene più risoluzioni a seconda delle specifiche di ciò che causa errori Mac).</span><span class="sxs-lookup"><span data-stu-id="15e25-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="15e25-108">Nome</span><span class="sxs-lookup"><span data-stu-id="15e25-108">Name</span></span>    | <span data-ttu-id="15e25-109">Valore</span><span class="sxs-lookup"><span data-stu-id="15e25-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="15e25-110">Scope</span><span class="sxs-lookup"><span data-stu-id="15e25-110">Scope</span></span>   |<span data-ttu-id="15e25-111">Principale</span><span class="sxs-lookup"><span data-stu-id="15e25-111">Major</span></span>|
|<span data-ttu-id="15e25-112">Version</span><span class="sxs-lookup"><span data-stu-id="15e25-112">Version</span></span>|<span data-ttu-id="15e25-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="15e25-113">4.5.2</span></span>|
|<span data-ttu-id="15e25-114">Type</span><span class="sxs-lookup"><span data-stu-id="15e25-114">Type</span></span>|<span data-ttu-id="15e25-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="15e25-115">Runtime</span></span>|
