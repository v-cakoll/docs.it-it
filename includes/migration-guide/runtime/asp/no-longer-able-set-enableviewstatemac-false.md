---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803176"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="4340d-101">Non è più possibile impostare EnableViewStateMac su false</span><span class="sxs-lookup"><span data-stu-id="4340d-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4340d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4340d-102">Details</span></span>|<span data-ttu-id="4340d-103">ASP.NET non consente più agli sviluppatori di specificare <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="4340d-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="4340d-104">L'algoritmo Message Authentication Code (MAC) dello stato di visualizzazione viene ora applicato per tutte le richieste con stato di visualizzazione incorporato.</span><span class="sxs-lookup"><span data-stu-id="4340d-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="4340d-105">Riguarda solo le app che impostano in modo esplicito la proprietà EnableViewStateMac su <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="4340d-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="4340d-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="4340d-106">Suggestion</span></span>|<span data-ttu-id="4340d-107">EnableViewStateMac deve essere considerato true e tutti gli errori MAC risultanti devono essere risolti (come spiegato in [questa guida](https://support.microsoft.com/kb/2915218), che contiene più risoluzioni a seconda delle specifiche di ciò che causa gli errori MAC).</span><span class="sxs-lookup"><span data-stu-id="4340d-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="4340d-108">Scope</span><span class="sxs-lookup"><span data-stu-id="4340d-108">Scope</span></span>|<span data-ttu-id="4340d-109">Principale</span><span class="sxs-lookup"><span data-stu-id="4340d-109">Major</span></span>|
|<span data-ttu-id="4340d-110">Versione</span><span class="sxs-lookup"><span data-stu-id="4340d-110">Version</span></span>|<span data-ttu-id="4340d-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="4340d-111">4.5.2</span></span>|
|<span data-ttu-id="4340d-112">Type</span><span class="sxs-lookup"><span data-stu-id="4340d-112">Type</span></span>|<span data-ttu-id="4340d-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="4340d-113">Runtime</span></span>|
