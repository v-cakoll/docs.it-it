---
ms.openlocfilehash: 49041ce906ab0bb8b9482b79c44302465c4ca788
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702268"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="2db6c-101">API di globalizzazione usare le librerie ICU in Windows</span><span class="sxs-lookup"><span data-stu-id="2db6c-101">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="2db6c-102">.NET 5,0 e versioni successive usano le librerie [International Components for Unicode (ICU)](http://site.icu-project.org/home) per la globalizzazione durante l'esecuzione in Windows 10 May 2019 Update o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="2db6c-102">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2db6c-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="2db6c-103">Change description</span></span>

<span data-ttu-id="2db6c-104">In precedenza, le librerie .NET usavano le API [NLS (National Language Support)](/windows/win32/intl/national-language-support) per la funzionalità di globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="2db6c-104">Previously, .NET libraries used [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality.</span></span> <span data-ttu-id="2db6c-105">Ad esempio, le funzioni NLS sono state usate per ottenere i dati delle impostazioni cultura, ad esempio i modelli di formato di data e ora, confrontare le stringhe ed eseguire le maiuscole e minuscole nelle impostazioni cultura appropriate.</span><span class="sxs-lookup"><span data-stu-id="2db6c-105">For example, NLS functions were used to get culture data, such as date and time format patterns, compare strings, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="2db6c-106">A partire da .NET 5,0, se un'app è in esecuzione in Windows 10 May 2019 Update o versioni successive, le librerie .NET usano le API di globalizzazione di [ICU](http://site.icu-project.org/home) .</span><span class="sxs-lookup"><span data-stu-id="2db6c-106">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs.</span></span> <span data-ttu-id="2db6c-107">Windows 10 May 2019 Update e versioni successive vengono forniti con la libreria nativa di ICU.</span><span class="sxs-lookup"><span data-stu-id="2db6c-107">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="2db6c-108">Se il Runtime .NET non è in grado di caricare ICU, USA invece NLS.</span><span class="sxs-lookup"><span data-stu-id="2db6c-108">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

<span data-ttu-id="2db6c-109">Questa modifica è stata introdotta per due motivi:</span><span class="sxs-lookup"><span data-stu-id="2db6c-109">This change was introduced for two reasons:</span></span>

- <span data-ttu-id="2db6c-110">Le app hanno lo stesso comportamento di globalizzazione su più piattaforme, tra cui Linux, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="2db6c-110">Apps have the same globalization behavior across platforms, including Linux, macOS, and Windows.</span></span>
- <span data-ttu-id="2db6c-111">Le app possono controllare il comportamento di globalizzazione usando librerie ICU personalizzate.</span><span class="sxs-lookup"><span data-stu-id="2db6c-111">Apps can control globalization behavior by using custom ICU libraries.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2db6c-112">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2db6c-112">Version introduced</span></span>

<span data-ttu-id="2db6c-113">.NET 5,0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="2db6c-113">.NET 5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2db6c-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2db6c-114">Recommended action</span></span>

<span data-ttu-id="2db6c-115">Non è richiesta alcuna azione da parte dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="2db6c-115">No action is required on the part of the developer.</span></span> <span data-ttu-id="2db6c-116">Tuttavia, se si desidera continuare a utilizzare le API di globalizzazione NLS, è possibile impostare un' [opzione di run-time](../../../../docs/core/run-time-config/globalization.md#nls) per ripristinare il comportamento.</span><span class="sxs-lookup"><span data-stu-id="2db6c-116">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../../docs/core/run-time-config/globalization.md#nls) to revert to that behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="2db6c-117">Category</span><span class="sxs-lookup"><span data-stu-id="2db6c-117">Category</span></span>

<span data-ttu-id="2db6c-118">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="2db6c-118">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2db6c-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="2db6c-119">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="2db6c-120">Molti tipi nello <xref:System.Globalization?displayProperty=fullName> spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="2db6c-120">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>

<!--

#### Affected APIs

- `T:System.Span%601`
- `T:System.String`
- `N:System.Globalization`

-->
