---
ms.openlocfilehash: c103dff320ae30d02c12ea5c585a47b589da8237
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621307"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a><span data-ttu-id="74fdc-101">ContentDisposition DateTimes restituisce una stringa leggermente diversa</span><span class="sxs-lookup"><span data-stu-id="74fdc-101">ContentDisposition DateTimes returns slightly different string</span></span>

#### <a name="details"></a><span data-ttu-id="74fdc-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="74fdc-102">Details</span></span>

<span data-ttu-id="74fdc-103">Le rappresentazioni di stringa di <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> sono state aggiornate, a partire dalla versione 4.6, in modo da rappresentare sempre il componente dell'ora di un valore <xref:System.DateTime?displayProperty=fullName> con due cifre.</span><span class="sxs-lookup"><span data-stu-id="74fdc-103">String representations of <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>'s have been updated, beginning in 4.6, to always represent the hour component of a <xref:System.DateTime?displayProperty=fullName> with two digits.</span></span> <span data-ttu-id="74fdc-104">Questo comportamento è conforme a [RFC822](https://www.ietf.org/rfc/rfc0822.txt) e [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span><span class="sxs-lookup"><span data-stu-id="74fdc-104">This is to comply with [RFC822](https://www.ietf.org/rfc/rfc0822.txt) and [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span></span> <span data-ttu-id="74fdc-105">Ne consegue che <xref:System.Net.Mime.ContentDisposition.ToString> restituisce una stringa leggermente diversa nella versione 4.6 negli scenari in cui uno degli elementi di tempo della disposizione precede le 10.00.</span><span class="sxs-lookup"><span data-stu-id="74fdc-105">This causes <xref:System.Net.Mime.ContentDisposition.ToString> to return a slightly different string in 4.6 in scenarios where one of the disposition's time elements was before 10:00 AM.</span></span> <span data-ttu-id="74fdc-106">Si noti che i valori di ContentDisposition vengono a volte serializzati convertendoli in stringhe, pertanto è necessario verificare qualsiasi operazione <xref:System.Net.Mime.ContentDisposition.ToString>, la serializzazione o le chiamate di GetHashCode.</span><span class="sxs-lookup"><span data-stu-id="74fdc-106">Note that ContentDispositions are sometimes serialized via converting them to strings, so any <xref:System.Net.Mime.ContentDisposition.ToString> operations, serialization, or GetHashCode calls should be reviewed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="74fdc-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="74fdc-107">Suggestion</span></span>

<span data-ttu-id="74fdc-108">Non dare per scontato che le rappresentazioni di stringa di ContentDisposition da versioni diverse di .NET Framework vengano confrontate correttamente.</span><span class="sxs-lookup"><span data-stu-id="74fdc-108">Do not expect that string representations of ContentDispositions from different .NET Framework versions will correctly compare to one another.</span></span> <span data-ttu-id="74fdc-109">Se possibile, riconvertire le stringhe in ContentDisposition prima di eseguire un confronto.</span><span class="sxs-lookup"><span data-stu-id="74fdc-109">Convert the strings back to ContentDispositions, if possible, before conducting a comparison.</span></span>

| <span data-ttu-id="74fdc-110">Nome</span><span class="sxs-lookup"><span data-stu-id="74fdc-110">Name</span></span>    | <span data-ttu-id="74fdc-111">Valore</span><span class="sxs-lookup"><span data-stu-id="74fdc-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="74fdc-112">Scope</span><span class="sxs-lookup"><span data-stu-id="74fdc-112">Scope</span></span>   |<span data-ttu-id="74fdc-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="74fdc-113">Minor</span></span>|
|<span data-ttu-id="74fdc-114">Version</span><span class="sxs-lookup"><span data-stu-id="74fdc-114">Version</span></span>|<span data-ttu-id="74fdc-115">4.6</span><span class="sxs-lookup"><span data-stu-id="74fdc-115">4.6</span></span>|
|<span data-ttu-id="74fdc-116">Type</span><span class="sxs-lookup"><span data-stu-id="74fdc-116">Type</span></span>|<span data-ttu-id="74fdc-117">Runtime</span><span class="sxs-lookup"><span data-stu-id="74fdc-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="74fdc-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="74fdc-118">Affected APIs</span></span>

-<xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType></li><li><xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType></li></ul>|
