---
ms.openlocfilehash: d35de48dd22003c851cf5dba9e8517ec48b9217b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567776"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a><span data-ttu-id="97667-101">Le impostazioni locali "C" vengono mappate alle impostazioni locali invarianti</span><span class="sxs-lookup"><span data-stu-id="97667-101">"C" locale maps to the invariant locale</span></span>

<span data-ttu-id="97667-102">.NET Core 2.2 e versioni precedenti dipendono dal comportamento di iCU predefinito, che esegue il mapping delle impostazioni locali "C" alle impostazioni locali en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="97667-102">.NET Core 2.2 and earlier versions depend on the default ICU behavior, which maps the "C" locale to the en_US_POSIX locale.</span></span> <span data-ttu-id="97667-103">Il en_US_POSIX impostazioni locali ha un comportamento di confronto indesiderato, perché non supporta i confronti tra stringhe senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="97667-103">The en_US_POSIX locale has an undesirable collation behavior, because it doesn't support case-insensitive string comparisons.</span></span> <span data-ttu-id="97667-104">Poiché alcune distribuzioni Linux impostano le impostazioni locali "C" come impostazioni locali predefinite, gli utenti riscontravano un comportamento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="97667-104">Because some Linux distributions set the "C" locale as the default locale, users were experiencing unexpected behavior.</span></span>

#### <a name="change-description"></a><span data-ttu-id="97667-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="97667-105">Change description</span></span>

<span data-ttu-id="97667-106">A partire da .NET Core 3.0, il mapping delle impostazioni locali "C" è stato modificato per utilizzare le impostazioni locali invarianti anziché en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="97667-106">Starting with .NET Core 3.0, the "C" locale mapping has changed to use the Invariant locale instead of en_US_POSIX.</span></span> <span data-ttu-id="97667-107">Le impostazioni locali "C" per il mapping invariante vengono applicate anche a Windows per coerenza.</span><span class="sxs-lookup"><span data-stu-id="97667-107">The "C" locale to Invariant mapping is also applied to Windows for consistency.</span></span>

<span data-ttu-id="97667-108">Il mapping di "C" alle impostazioni cultura en_US_POSIX ha causato confusione tra i clienti, poiché en_US_POSIX non supporta le operazioni di ordinamento/ricerca delle stringhe senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="97667-108">Mapping "C" to en_US_POSIX culture caused customer confusion, because en_US_POSIX doesn't support case insensitive sorting/searching string operations.</span></span> <span data-ttu-id="97667-109">Poiché le impostazioni locali "C" vengono utilizzate come impostazioni locali predefinite in alcune delle distribuzioni Linux, i clienti hanno sperimentato questo comportamento indesiderato in questi sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="97667-109">Because the "C" locale is used as a default locale in some of the Linux distros, customers experienced this undesired behavior on these operating systems.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="97667-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="97667-110">Version introduced</span></span>

<span data-ttu-id="97667-111">3.0</span><span class="sxs-lookup"><span data-stu-id="97667-111">3.0</span></span>

### <a name="recommended-action"></a><span data-ttu-id="97667-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="97667-112">Recommended action</span></span>

<span data-ttu-id="97667-113">Niente di più specifico della consapevolezza di questo cambiamento.</span><span class="sxs-lookup"><span data-stu-id="97667-113">Nothing specific more than the awareness of this change.</span></span> <span data-ttu-id="97667-114">Questa modifica interessa solo le applicazioni che utilizzano il mapping delle impostazioni locali "C".</span><span class="sxs-lookup"><span data-stu-id="97667-114">This change affects only applications that use the "C" locale mapping.</span></span>

### <a name="category"></a><span data-ttu-id="97667-115">Category</span><span class="sxs-lookup"><span data-stu-id="97667-115">Category</span></span>

<span data-ttu-id="97667-116">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="97667-116">Globalization</span></span>

### <a name="affected-apis"></a><span data-ttu-id="97667-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="97667-117">Affected APIs</span></span>

<span data-ttu-id="97667-118">Tutte le regole di confronto e le API delle impostazioni cultura sono interessate da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="97667-118">All collation and culture APIs are affected by this change.</span></span>

<!--

-->
