---
title: 'Metodo IXCLRDataMethodInstance:: GetILAddressMap'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7c4dcf59ce159434d5012120043f5bb548d49731
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396811"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="17d62-102">Metodo IXCLRDataMethodInstance:: GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="17d62-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="17d62-103">Ottiene l'oggetto per l'indirizzamento delle informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="17d62-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="17d62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17d62-104">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="17d62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17d62-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="17d62-106">in Lunghezza della matrice di mappe specificata.</span><span class="sxs-lookup"><span data-stu-id="17d62-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="17d62-107">out Numero di voci della mappa necessarie per il metodo.</span><span class="sxs-lookup"><span data-stu-id="17d62-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="17d62-108">[out, size_is (mapLen)] Matrice per l'archiviazione delle voci della mappa.</span><span class="sxs-lookup"><span data-stu-id="17d62-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="17d62-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="17d62-109">Remarks</span></span>

<span data-ttu-id="17d62-110">Il metodo fornito fa parte dell' `IXCLRDataMethodInstance` interfaccia e corrisponde al quindicesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="17d62-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 15th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="17d62-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17d62-111">Requirements</span></span>

<span data-ttu-id="17d62-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17d62-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="17d62-113">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="17d62-113">**Header:** None</span></span>  
<span data-ttu-id="17d62-114">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="17d62-114">**Library:** None</span></span>  
<span data-ttu-id="17d62-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="17d62-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="17d62-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="17d62-116">See also</span></span>

- [<span data-ttu-id="17d62-117">Debug</span><span class="sxs-lookup"><span data-stu-id="17d62-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="17d62-118">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="17d62-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
