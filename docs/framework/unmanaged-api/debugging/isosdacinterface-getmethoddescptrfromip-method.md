---
title: Metodo ISOSDacInterface::GetMethodDescPtrFromIP
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 74853733b1fb7f023d9f192d3e862dbf6875ecda
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828657"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="03e16-102">Metodo ISOSDacInterface::GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="03e16-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="03e16-103">Recupera il puntatore del MethodDesc corrispondente metodo contenente l'indirizzo dell'istruzione nativo specificato.</span><span class="sxs-lookup"><span data-stu-id="03e16-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="03e16-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03e16-104">Syntax</span></span>

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

### <a name="parameters"></a><span data-ttu-id="03e16-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03e16-105">Parameters</span></span>

<span data-ttu-id="03e16-106">`ip` [in] Un indirizzo all'interno del metodo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="03e16-106">`ip` [in] An address within the method at runtime.</span></span>

<span data-ttu-id="03e16-107">`ppMD` [out] L'indirizzo del `MethodDesc` per il metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="03e16-107">`ppMD` [out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="03e16-108">Note</span><span class="sxs-lookup"><span data-stu-id="03e16-108">Remarks</span></span>

<span data-ttu-id="03e16-109">Il metodo specificato fa parte di [ `ISOSDacInterface` interfaccia](isosdacinterface-interface.md) e corrisponde al 21 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="03e16-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="03e16-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03e16-110">Requirements</span></span>

<span data-ttu-id="03e16-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03e16-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="03e16-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="03e16-112">**Header:** None</span></span>  
<span data-ttu-id="03e16-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="03e16-113">**Library:** None</span></span>  
<span data-ttu-id="03e16-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="03e16-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="03e16-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03e16-115">See also</span></span>

- [<span data-ttu-id="03e16-116">Debug</span><span class="sxs-lookup"><span data-stu-id="03e16-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="03e16-117">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="03e16-117">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
