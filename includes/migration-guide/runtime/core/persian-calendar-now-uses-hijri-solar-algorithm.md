---
ms.openlocfilehash: e4d9efe7d2a06a1e501b070c23184dcd913dba71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621283"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="67ada-101">Il calendario persiano ora usa l'algoritmo solare Hijri</span><span class="sxs-lookup"><span data-stu-id="67ada-101">Persian calendar now uses the Hijri solar algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="67ada-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="67ada-102">Details</span></span>

<span data-ttu-id="67ada-103">A partire da .NET Framework 4.6, la classe <xref:System.Globalization.PersianCalendar?displayProperty=fullName> usa l'algoritmo solare Hijri.</span><span class="sxs-lookup"><span data-stu-id="67ada-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="67ada-104">La conversione di date tra il calendario <xref:System.Globalization.PersianCalendar?displayProperty=fullName> e altri calendari può produrre risultati leggermente diversi a partire da .NET Framework 4.6 per le date precedenti al 1800 o successive al 2023 (calendario gregoriano). Inoltre, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> è ora <code>March 22, 0622</code> invece di <code>March 21, 0622</code>.</span><span class="sxs-lookup"><span data-stu-id="67ada-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> is now <code>March 22, 0622</code> instead of <code>March 21, 0622</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="67ada-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="67ada-105">Suggestion</span></span>

<span data-ttu-id="67ada-106">Tenere presente che alcune date precedenti o successive potrebbero essere leggermente diverse quando si usa PersianCalendar in .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="67ada-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET Framework 4.6.</span></span> <span data-ttu-id="67ada-107">Inoltre, quando si serializzano le date tra processi che possono essere eseguiti in versioni diverse di .NET Framework, evitare di archiviarle come stringhe di data PersianCalendar, perché tali valori potrebbero essere diversi.</span><span class="sxs-lookup"><span data-stu-id="67ada-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>

| <span data-ttu-id="67ada-108">Nome</span><span class="sxs-lookup"><span data-stu-id="67ada-108">Name</span></span>    | <span data-ttu-id="67ada-109">Valore</span><span class="sxs-lookup"><span data-stu-id="67ada-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="67ada-110">Scope</span><span class="sxs-lookup"><span data-stu-id="67ada-110">Scope</span></span>   |<span data-ttu-id="67ada-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="67ada-111">Minor</span></span>|
|<span data-ttu-id="67ada-112">Version</span><span class="sxs-lookup"><span data-stu-id="67ada-112">Version</span></span>|<span data-ttu-id="67ada-113">4.6</span><span class="sxs-lookup"><span data-stu-id="67ada-113">4.6</span></span>|
|<span data-ttu-id="67ada-114">Type</span><span class="sxs-lookup"><span data-stu-id="67ada-114">Type</span></span>|<span data-ttu-id="67ada-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="67ada-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="67ada-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="67ada-116">Affected APIs</span></span>

-<xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
