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
ms.openlocfilehash: 0c8d91c11205e06857b4a6e7edfedcd087270d00
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396932"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="7ff6d-102">Metodo ISOSDacInterface:: GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="7ff6d-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="7ff6d-103">Recupera il puntatore di MethodDesc corrispondente al metodo che contiene l'indirizzo di istruzione nativo specificato.</span><span class="sxs-lookup"><span data-stu-id="7ff6d-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7ff6d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ff6d-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="7ff6d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ff6d-105">Parameters</span></span>

`ip`\
<span data-ttu-id="7ff6d-106">in Un indirizzo all'interno del metodo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7ff6d-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="7ff6d-107">out Indirizzo dell'oggetto `MethodDesc` per il metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="7ff6d-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ff6d-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="7ff6d-108">Remarks</span></span>

<span data-ttu-id="7ff6d-109">Il metodo fornito fa parte dell' [ `ISOSDacInterface` interfaccia](isosdacinterface-interface.md) e corrisponde al ventiduesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="7ff6d-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ff6d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ff6d-110">Requirements</span></span>

<span data-ttu-id="7ff6d-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ff6d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7ff6d-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="7ff6d-112">**Header:** None</span></span>  
<span data-ttu-id="7ff6d-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="7ff6d-113">**Library:** None</span></span>  
<span data-ttu-id="7ff6d-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7ff6d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7ff6d-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7ff6d-115">See also</span></span>

- [<span data-ttu-id="7ff6d-116">Debug</span><span class="sxs-lookup"><span data-stu-id="7ff6d-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="7ff6d-117">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="7ff6d-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
