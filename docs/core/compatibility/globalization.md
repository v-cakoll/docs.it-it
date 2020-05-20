---
title: Modifiche di rilievo della globalizzazione
description: Elenca le modifiche di rilievo della globalizzazione in .NET Core.
ms.date: 04/07/2020
ms.openlocfilehash: 0c3367cb3515c6f473f53be6062b54f2e836b8c5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702256"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="229f2-103">Modifiche di rilievo della globalizzazione</span><span class="sxs-lookup"><span data-stu-id="229f2-103">Globalization breaking changes</span></span>

<span data-ttu-id="229f2-104">In questa pagina sono documentate le modifiche di rilievo seguenti:</span><span class="sxs-lookup"><span data-stu-id="229f2-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="229f2-105">Modifica</span><span class="sxs-lookup"><span data-stu-id="229f2-105">Breaking change</span></span> | <span data-ttu-id="229f2-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="229f2-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="229f2-107">API di globalizzazione usare le librerie ICU in Windows</span><span class="sxs-lookup"><span data-stu-id="229f2-107">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="229f2-108">5.0</span><span class="sxs-lookup"><span data-stu-id="229f2-108">5.0</span></span> |
| [<span data-ttu-id="229f2-109">StringInfo e TextElementEnumerator ora sono conformi a UAX29</span><span class="sxs-lookup"><span data-stu-id="229f2-109">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="229f2-110">5.0</span><span class="sxs-lookup"><span data-stu-id="229f2-110">5.0</span></span> |
| [<span data-ttu-id="229f2-111">Le impostazioni locali "C" sono mappate alle impostazioni locali invariabili</span><span class="sxs-lookup"><span data-stu-id="229f2-111">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="229f2-112">3.0</span><span class="sxs-lookup"><span data-stu-id="229f2-112">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="229f2-113">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="229f2-113">.NET 5.0</span></span>

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="229f2-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="229f2-114">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
