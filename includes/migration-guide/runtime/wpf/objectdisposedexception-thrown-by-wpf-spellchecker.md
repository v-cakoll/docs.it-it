---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621803"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="262a4-101">ObjectDisposedException generata dal controllo ortografico WPF</span><span class="sxs-lookup"><span data-stu-id="262a4-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="262a4-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="262a4-102">Details</span></span>

<span data-ttu-id="262a4-103">Può verificarsi l'arresto anomalo di applicazioni WPF con un <xref:System.ObjectDisposedException?displayProperty=fullName> generato dal controllo ortografico.</span><span class="sxs-lookup"><span data-stu-id="262a4-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="262a4-104">Questo problema è risolto in .NET Framework 4.7 WPF, dove l'eccezione viene gestita in modo normale e pertanto si evitano effetti avversi sulle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="262a4-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="262a4-105">Si noti che potranno essere rilevate eccezioni first-chance occasionali nelle applicazioni in esecuzione in un debugger.</span><span class="sxs-lookup"><span data-stu-id="262a4-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="262a4-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="262a4-106">Suggestion</span></span>

<span data-ttu-id="262a4-107">Effettuare l'aggiornamento a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="262a4-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="262a4-108">Nome</span><span class="sxs-lookup"><span data-stu-id="262a4-108">Name</span></span>    | <span data-ttu-id="262a4-109">Valore</span><span class="sxs-lookup"><span data-stu-id="262a4-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="262a4-110">Scope</span><span class="sxs-lookup"><span data-stu-id="262a4-110">Scope</span></span>   |<span data-ttu-id="262a4-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="262a4-111">Edge</span></span>|
|<span data-ttu-id="262a4-112">Version</span><span class="sxs-lookup"><span data-stu-id="262a4-112">Version</span></span>|<span data-ttu-id="262a4-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="262a4-113">4.6.1</span></span>|
|<span data-ttu-id="262a4-114">Type</span><span class="sxs-lookup"><span data-stu-id="262a4-114">Type</span></span>|<span data-ttu-id="262a4-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="262a4-115">Runtime</span></span>|
