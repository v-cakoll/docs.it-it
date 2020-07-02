---
ms.openlocfilehash: d4f0095bc9fde98087dce528c8154d9c9ac6ddb7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621804"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="e46d9-101">Il controllo ortografico in WPF restituisce errori imprevisti</span><span class="sxs-lookup"><span data-stu-id="e46d9-101">WPF Spell Checking fails in unexpected ways</span></span>

#### <a name="details"></a><span data-ttu-id="e46d9-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e46d9-102">Details</span></span>

<span data-ttu-id="e46d9-103">Questa condizione riunisce vari problemi riscontrati con il controllo ortografico WPF:</span><span class="sxs-lookup"><span data-stu-id="e46d9-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="e46d9-104">In determinati casi il controllo ortografico WPF genera <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e46d9-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span></span></li><li><span data-ttu-id="e46d9-105">Il controllo ortografico WPF non riesce con <xref:System.UnauthorizedAccessException> quando le applicazioni vengono avviate usando "Esegui come altro utente"</span><span class="sxs-lookup"><span data-stu-id="e46d9-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="e46d9-106">Il controllo ortografico WPF identifica in modo errato gli errori di ortografia di parole composte, ad esempio "Hausnummer" in tedesco.</span><span class="sxs-lookup"><span data-stu-id="e46d9-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="e46d9-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="e46d9-107">Suggestion</span></span>

<span data-ttu-id="e46d9-108">Problema n. 1: risolto in .NET Framework 4.6.2. Problema n. 2: il controllo ortografico WPF non è più supportato quando le applicazioni vengono avviate usando l'opzione "Esegui come altro utente".</span><span class="sxs-lookup"><span data-stu-id="e46d9-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="e46d9-109">A partire da .NET Framework 4.6.2, le applicazioni avviate in questo modo non si arrestano più in modo anomalo, ma il controllo ortografico viene disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e46d9-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="e46d9-110">Problema n. 3: risolto in .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="e46d9-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="e46d9-111">Nome</span><span class="sxs-lookup"><span data-stu-id="e46d9-111">Name</span></span>    | <span data-ttu-id="e46d9-112">Valore</span><span class="sxs-lookup"><span data-stu-id="e46d9-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e46d9-113">Scope</span><span class="sxs-lookup"><span data-stu-id="e46d9-113">Scope</span></span>   |<span data-ttu-id="e46d9-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e46d9-114">Edge</span></span>|
|<span data-ttu-id="e46d9-115">Version</span><span class="sxs-lookup"><span data-stu-id="e46d9-115">Version</span></span>|<span data-ttu-id="e46d9-116">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e46d9-116">4.6.1</span></span>|
|<span data-ttu-id="e46d9-117">Type</span><span class="sxs-lookup"><span data-stu-id="e46d9-117">Type</span></span>|<span data-ttu-id="e46d9-118">Runtime</span><span class="sxs-lookup"><span data-stu-id="e46d9-118">Runtime</span></span>|
