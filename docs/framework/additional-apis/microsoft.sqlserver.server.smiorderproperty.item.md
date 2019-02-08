---
title: Proprietà SmiOrderProperty.Item (SqlServer)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: cb2f6cb956f9571f9bd2ba7f86d79c5df6e72a15
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827734"
---
# <a name="smiorderpropertyitem-property"></a><span data-ttu-id="76f18-102">Proprietà SmiOrderProperty.Item</span><span class="sxs-lookup"><span data-stu-id="76f18-102">SmiOrderProperty.Item Property</span></span>

<span data-ttu-id="76f18-103">Ottiene l'ordine delle colonne per l'entità.</span><span class="sxs-lookup"><span data-stu-id="76f18-103">Gets the column order for the entity.</span></span> <span data-ttu-id="76f18-104">L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess.</span><span class="sxs-lookup"><span data-stu-id="76f18-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="76f18-105">Si tratta per l'uso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="76f18-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="76f18-106">Per altri database, usare il meccanismo di hosting fornito da tale database.</span><span class="sxs-lookup"><span data-stu-id="76f18-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="76f18-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76f18-107">Syntax</span></span>

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a><span data-ttu-id="76f18-108">Valore della proprietà</span><span class="sxs-lookup"><span data-stu-id="76f18-108">Property value</span></span>

<span data-ttu-id="76f18-109">L'ordine delle colonne.</span><span class="sxs-lookup"><span data-stu-id="76f18-109">The column order.</span></span>

## <a name="remarks"></a><span data-ttu-id="76f18-110">Note</span><span class="sxs-lookup"><span data-stu-id="76f18-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="76f18-111">Il `SmiOrderProperty.Item` proprietà sono interna e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="76f18-111">The `SmiOrderProperty.Item` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="76f18-112">Microsoft non supporta l'uso di questa proprietà in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="76f18-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="76f18-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76f18-113">Requirements</span></span>

<span data-ttu-id="76f18-114">**Spazio dei nomi:** <xref:Microsoft.SqlServer.Server></span><span class="sxs-lookup"><span data-stu-id="76f18-114">**Namespace:** <xref:Microsoft.SqlServer.Server></span></span>

<span data-ttu-id="76f18-115">**Assembly:** System. Data (in System)</span><span class="sxs-lookup"><span data-stu-id="76f18-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="76f18-116">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="76f18-116">**.NET Framework versions:** Available since 2.0.</span></span>