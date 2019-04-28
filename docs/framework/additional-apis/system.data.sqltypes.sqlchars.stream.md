---
title: Proprietà SqlChars.Stream (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4858d9f8878e5b56a0811edf92a2faa729775156
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675201"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="93809-102">SqlChars.Stream Property</span><span class="sxs-lookup"><span data-stu-id="93809-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="93809-103">Ottiene o imposta il flusso di caratteri.</span><span class="sxs-lookup"><span data-stu-id="93809-103">Gets or sets the character stream.</span></span> <span data-ttu-id="93809-104">L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="93809-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="93809-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="93809-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="93809-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="93809-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="93809-107">Valore della proprietà</span><span class="sxs-lookup"><span data-stu-id="93809-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="93809-108">Il flusso di caratteri.</span><span class="sxs-lookup"><span data-stu-id="93809-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="93809-109">Note</span><span class="sxs-lookup"><span data-stu-id="93809-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="93809-110">Il `SqlChars.Stream` proprietà sono interna e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="93809-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="93809-111">Microsoft non supporta l'uso di questa proprietà in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="93809-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="93809-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93809-112">Requirements</span></span>

<span data-ttu-id="93809-113">**Spazio dei nomi:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="93809-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="93809-114">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="93809-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="93809-115">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="93809-115">**.NET Framework versions:** Available since 2.0.</span></span>