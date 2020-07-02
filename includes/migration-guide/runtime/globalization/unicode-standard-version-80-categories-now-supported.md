---
ms.openlocfilehash: a20fad5f9c95e59c14ffd91f4921cf8bfab443cd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621187"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="4ab7a-101">Le categorie dello standard Unicode versione 8.0 sono ora supportate</span><span class="sxs-lookup"><span data-stu-id="4ab7a-101">Unicode standard version 8.0 categories now supported</span></span>

#### <a name="details"></a><span data-ttu-id="4ab7a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4ab7a-102">Details</span></span>

<span data-ttu-id="4ab7a-103">In .NET Framework 4.6.2 i dati Unicode sono stati aggiornati dallo standard Unicode versione 6.3 alla versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="4ab7a-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="4ab7a-104">Quando si richiedono le categorie di caratteri Unicode in .NET Framework 4.6.2, alcuni risultati potrebbero non corrispondere ai risultati ottenuti nelle versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ab7a-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="4ab7a-105">Questa modifica interessa principalmente le sillabe Cherokee e i simboli delle vocali e dei toni di Tai Lue semplificato.</span><span class="sxs-lookup"><span data-stu-id="4ab7a-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4ab7a-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="4ab7a-106">Suggestion</span></span>

<span data-ttu-id="4ab7a-107">Esaminare il codice e rimuovere o modificare la logica che dipende dalle categorie di caratteri Unicode hardcoded.</span><span class="sxs-lookup"><span data-stu-id="4ab7a-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>

| <span data-ttu-id="4ab7a-108">Nome</span><span class="sxs-lookup"><span data-stu-id="4ab7a-108">Name</span></span>    | <span data-ttu-id="4ab7a-109">Valore</span><span class="sxs-lookup"><span data-stu-id="4ab7a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4ab7a-110">Scope</span><span class="sxs-lookup"><span data-stu-id="4ab7a-110">Scope</span></span>   |<span data-ttu-id="4ab7a-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="4ab7a-111">Minor</span></span>|
|<span data-ttu-id="4ab7a-112">Version</span><span class="sxs-lookup"><span data-stu-id="4ab7a-112">Version</span></span>|<span data-ttu-id="4ab7a-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="4ab7a-113">4.6.2</span></span>|
|<span data-ttu-id="4ab7a-114">Type</span><span class="sxs-lookup"><span data-stu-id="4ab7a-114">Type</span></span>|<span data-ttu-id="4ab7a-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="4ab7a-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4ab7a-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="4ab7a-116">Affected APIs</span></span>

-<xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
