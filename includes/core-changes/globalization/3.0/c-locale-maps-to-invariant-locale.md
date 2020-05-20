---
ms.openlocfilehash: c0551fa086644497c631cd9b6d7058398ff9ccfa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702327"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a><span data-ttu-id="853f2-101">Le impostazioni locali "C" sono mappate alle impostazioni locali invariabili</span><span class="sxs-lookup"><span data-stu-id="853f2-101">"C" locale maps to the invariant locale</span></span>

<span data-ttu-id="853f2-102">.NET Core 2,2 e versioni precedenti dipendono dal comportamento ICU predefinito, che esegue il mapping delle impostazioni locali "C" alle impostazioni locali del en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="853f2-102">.NET Core 2.2 and earlier versions depend on the default ICU behavior, which maps the "C" locale to the en_US_POSIX locale.</span></span> <span data-ttu-id="853f2-103">Le impostazioni locali en_US_POSIX hanno un comportamento indesiderato per le regole di confronto, poiché non supporta confronti tra stringhe senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="853f2-103">The en_US_POSIX locale has an undesirable collation behavior, because it doesn't support case-insensitive string comparisons.</span></span> <span data-ttu-id="853f2-104">Poiché alcune distribuzioni di Linux impostano le impostazioni locali "C" come impostazioni locali predefinite, si è verificato un comportamento imprevisto per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="853f2-104">Because some Linux distributions set the "C" locale as the default locale, users were experiencing unexpected behavior.</span></span>

#### <a name="change-description"></a><span data-ttu-id="853f2-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="853f2-105">Change description</span></span>

<span data-ttu-id="853f2-106">A partire da .NET Core 3,0, il mapping delle impostazioni locali "C" è stato modificato in modo da usare le impostazioni locali invariabili anziché en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="853f2-106">Starting with .NET Core 3.0, the "C" locale mapping has changed to use the Invariant locale instead of en_US_POSIX.</span></span> <span data-ttu-id="853f2-107">Le impostazioni locali "C" al mapping invariante vengono applicate anche a Windows per coerenza.</span><span class="sxs-lookup"><span data-stu-id="853f2-107">The "C" locale to Invariant mapping is also applied to Windows for consistency.</span></span>

<span data-ttu-id="853f2-108">Il mapping di "C" alle impostazioni cultura en_US_POSIX ha causato confusione del cliente, perché en_US_POSIX non supporta operazioni di ordinamento/ricerca di stringhe senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="853f2-108">Mapping "C" to en_US_POSIX culture caused customer confusion, because en_US_POSIX doesn't support case insensitive sorting/searching string operations.</span></span> <span data-ttu-id="853f2-109">Poiché le impostazioni locali "C" vengono usate come impostazioni locali predefinite in alcune distribuzioni di Linux, i clienti hanno riscontrato questo comportamento indesiderato su questi sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="853f2-109">Because the "C" locale is used as a default locale in some of the Linux distros, customers experienced this undesired behavior on these operating systems.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="853f2-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="853f2-110">Version introduced</span></span>

<span data-ttu-id="853f2-111">3.0</span><span class="sxs-lookup"><span data-stu-id="853f2-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="853f2-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="853f2-112">Recommended action</span></span>

<span data-ttu-id="853f2-113">Niente di più della conoscenza di questa modifica.</span><span class="sxs-lookup"><span data-stu-id="853f2-113">Nothing specific more than the awareness of this change.</span></span> <span data-ttu-id="853f2-114">Questa modifica interessa solo le applicazioni che usano il mapping delle impostazioni locali "C".</span><span class="sxs-lookup"><span data-stu-id="853f2-114">This change affects only applications that use the "C" locale mapping.</span></span>

#### <a name="category"></a><span data-ttu-id="853f2-115">Category</span><span class="sxs-lookup"><span data-stu-id="853f2-115">Category</span></span>

<span data-ttu-id="853f2-116">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="853f2-116">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="853f2-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="853f2-117">Affected APIs</span></span>

<span data-ttu-id="853f2-118">Questa modifica ha effetto su tutte le API per le regole di confronto e le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="853f2-118">All collation and culture APIs are affected by this change.</span></span>

<!--

#### Affected APIs

-->
