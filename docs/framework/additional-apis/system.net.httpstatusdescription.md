---
title: Classe HttpStatusDescription (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990393"
---
# <a name="httpstatusdescription-class"></a><span data-ttu-id="9f4ac-102">Classe HttpStatusDescription</span><span class="sxs-lookup"><span data-stu-id="9f4ac-102">HttpStatusDescription class</span></span>

<span data-ttu-id="9f4ac-103">Fornisce descrizioni dello stato HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-103">Provides standard HTTP status descriptions.</span></span> <span data-ttu-id="9f4ac-104">Questa classe non può essere ereditata.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-104">This class cannot be inherited.</span></span>

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> <span data-ttu-id="9f4ac-105">Questa classe è interna e non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="9f4ac-106">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="get-method"></a><span data-ttu-id="9f4ac-107">metodo Get</span><span class="sxs-lookup"><span data-stu-id="9f4ac-107">Get method</span></span>

<span data-ttu-id="9f4ac-108">Restituisce la descrizione associata al codice di stato HTTP specificato.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-108">Returns the description associated with the specified HTTP status code.</span></span>

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a><span data-ttu-id="9f4ac-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f4ac-109">Parameters</span></span>

<span data-ttu-id="9f4ac-110">`code` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="9f4ac-110">`code` <xref:System.Int32></span></span>

<span data-ttu-id="9f4ac-111">Codice di stato HTTP, ad esempio `404` .</span><span class="sxs-lookup"><span data-stu-id="9f4ac-111">The HTTP status code, for example, `404`.</span></span>

### <a name="return-value"></a><span data-ttu-id="9f4ac-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f4ac-112">Return value</span></span>

<xref:System.String?displayProperty=nameWithType>

<span data-ttu-id="9f4ac-113">Descrizione dello stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-113">The HTTP status description.</span></span>

## <a name="requirements"></a><span data-ttu-id="9f4ac-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f4ac-114">Requirements</span></span>

<span data-ttu-id="9f4ac-115">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="9f4ac-115">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="9f4ac-116">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="9f4ac-116">**Assembly:** System (in System.dll)</span></span>
