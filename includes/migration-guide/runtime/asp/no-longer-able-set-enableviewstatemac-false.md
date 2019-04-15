---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236644"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="7a016-101">Non è più possibile impostare EnableViewStateMac su false</span><span class="sxs-lookup"><span data-stu-id="7a016-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7a016-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7a016-102">Details</span></span>|<span data-ttu-id="7a016-103">ASP.NET non consente più agli sviluppatori di specificare <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="7a016-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="7a016-104">L'algoritmo Message Authentication Code (MAC) dello stato di visualizzazione viene ora applicato per tutte le richieste con stato di visualizzazione incorporato.</span><span class="sxs-lookup"><span data-stu-id="7a016-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="7a016-105">Riguarda solo le app che impostano in modo esplicito la proprietà EnableViewStateMac su <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="7a016-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="7a016-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7a016-106">Suggestion</span></span>|<span data-ttu-id="7a016-107">Partire dal presupposto che la proprietà EnableViewStateMac sia true e risolvere eventuali errori MAC risultanti, come spiegato in [queste istruzioni](https://support.microsoft.com/kb/2915218) che contengono più soluzioni in base alle cause specifiche degli errori MAC.</span><span class="sxs-lookup"><span data-stu-id="7a016-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="7a016-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="7a016-108">Scope</span></span>|<span data-ttu-id="7a016-109">Principale</span><span class="sxs-lookup"><span data-stu-id="7a016-109">Major</span></span>|
|<span data-ttu-id="7a016-110">Versione</span><span class="sxs-lookup"><span data-stu-id="7a016-110">Version</span></span>|<span data-ttu-id="7a016-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="7a016-111">4.5.2</span></span>|
|<span data-ttu-id="7a016-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="7a016-112">Type</span></span>|<span data-ttu-id="7a016-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="7a016-113">Runtime</span></span>|
