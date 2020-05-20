---
title: 'Metodo ISOSDacInterface:: GetMethodDescPtrFromIP'
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
ms.openlocfilehash: c3de9e5ffe23a13c126343c6f74f042bf1239609
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421007"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="172d4-102">Metodo ISOSDacInterface:: GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="172d4-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="172d4-103">Recupera il puntatore di MethodDesc corrispondente al metodo che contiene l'indirizzo di istruzione nativo specificato.</span><span class="sxs-lookup"><span data-stu-id="172d4-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="172d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="172d4-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="172d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="172d4-105">Parameters</span></span>

`ip`\
<span data-ttu-id="172d4-106">in Un indirizzo all'interno del metodo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="172d4-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="172d4-107">out Indirizzo dell'oggetto `MethodDesc` per il metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="172d4-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="172d4-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="172d4-108">Remarks</span></span>

<span data-ttu-id="172d4-109">Il metodo fornito fa parte dell' [ `ISOSDacInterface` interfaccia](isosdacinterface-interface.md) e corrisponde al ventiduesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="172d4-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="172d4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="172d4-110">Requirements</span></span>

<span data-ttu-id="172d4-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="172d4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="172d4-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="172d4-112">**Header:** None</span></span>  
<span data-ttu-id="172d4-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="172d4-113">**Library:** None</span></span>  
<span data-ttu-id="172d4-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="172d4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="172d4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="172d4-115">See also</span></span>

- [<span data-ttu-id="172d4-116">Debug</span><span class="sxs-lookup"><span data-stu-id="172d4-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="172d4-117">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="172d4-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
