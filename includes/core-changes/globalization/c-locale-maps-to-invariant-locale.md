---
ms.openlocfilehash: d35de48dd22003c851cf5dba9e8517ec48b9217b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198458"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a><span data-ttu-id="d5335-101">Le impostazioni locali "C" sono mappate alle impostazioni locali invariabili</span><span class="sxs-lookup"><span data-stu-id="d5335-101">"C" locale maps to the invariant locale</span></span>

<span data-ttu-id="d5335-102">.NET Core 2,2 e versioni precedenti dipendono dal comportamento ICU predefinito, che esegue il mapping delle impostazioni locali "C" alle impostazioni locali di en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="d5335-102">.NET Core 2.2 and earlier versions depend on the default ICU behavior, which maps the "C" locale to the en_US_POSIX locale.</span></span> <span data-ttu-id="d5335-103">Le impostazioni locali en_US_POSIX hanno un comportamento indesiderato per le regole di confronto, poiché non supporta confronti tra stringhe senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d5335-103">The en_US_POSIX locale has an undesirable collation behavior, because it doesn't support case-insensitive string comparisons.</span></span> <span data-ttu-id="d5335-104">Poiché alcune distribuzioni di Linux impostano le impostazioni locali "C" come impostazioni locali predefinite, si è verificato un comportamento imprevisto per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d5335-104">Because some Linux distributions set the "C" locale as the default locale, users were experiencing unexpected behavior.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d5335-105">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="d5335-105">Change description</span></span>

<span data-ttu-id="d5335-106">A partire da .NET Core 3,0, il mapping delle impostazioni locali "C" è stato modificato in modo da usare le impostazioni locali invariabili anziché en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="d5335-106">Starting with .NET Core 3.0, the "C" locale mapping has changed to use the Invariant locale instead of en_US_POSIX.</span></span> <span data-ttu-id="d5335-107">Le impostazioni locali "C" al mapping invariante vengono applicate anche a Windows per coerenza.</span><span class="sxs-lookup"><span data-stu-id="d5335-107">The "C" locale to Invariant mapping is also applied to Windows for consistency.</span></span>

<span data-ttu-id="d5335-108">Il mapping di "C" alla cultura en_US_POSIX ha causato confusione dei clienti, perché en_US_POSIX non supporta operazioni di ordinamento/ricerca di stringhe senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d5335-108">Mapping "C" to en_US_POSIX culture caused customer confusion, because en_US_POSIX doesn't support case insensitive sorting/searching string operations.</span></span> <span data-ttu-id="d5335-109">Poiché le impostazioni locali "C" vengono usate come impostazioni locali predefinite in alcune distribuzioni di Linux, i clienti hanno riscontrato questo comportamento indesiderato su questi sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="d5335-109">Because the "C" locale is used as a default locale in some of the Linux distros, customers experienced this undesired behavior on these operating systems.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d5335-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d5335-110">Version introduced</span></span>

<span data-ttu-id="d5335-111">3.0</span><span class="sxs-lookup"><span data-stu-id="d5335-111">3.0</span></span>

### <a name="recommended-action"></a><span data-ttu-id="d5335-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="d5335-112">Recommended action</span></span>

<span data-ttu-id="d5335-113">Niente di più della conoscenza di questa modifica.</span><span class="sxs-lookup"><span data-stu-id="d5335-113">Nothing specific more than the awareness of this change.</span></span> <span data-ttu-id="d5335-114">Questa modifica interessa solo le applicazioni che usano il mapping delle impostazioni locali "C".</span><span class="sxs-lookup"><span data-stu-id="d5335-114">This change affects only applications that use the "C" locale mapping.</span></span>

### <a name="category"></a><span data-ttu-id="d5335-115">Category</span><span class="sxs-lookup"><span data-stu-id="d5335-115">Category</span></span>

<span data-ttu-id="d5335-116">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="d5335-116">Globalization</span></span>

### <a name="affected-apis"></a><span data-ttu-id="d5335-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="d5335-117">Affected APIs</span></span>

<span data-ttu-id="d5335-118">Questa modifica ha effetto su tutte le API per le regole di confronto e le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="d5335-118">All collation and culture APIs are affected by this change.</span></span>

<!--

-->
