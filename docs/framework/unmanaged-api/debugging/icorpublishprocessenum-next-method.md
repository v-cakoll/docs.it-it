---
title: Metodo ICorPublishProcessEnum::Next
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: 084af87acd73ef65739ba69ef2bd66d10d7c27c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790522"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="0ea0a-102">Metodo ICorPublishProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="0ea0a-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="0ea0a-103">Ottiene il numero specificato di processi dalla raccolta, a partire dalla posizione corrente del cursore.</span><span class="sxs-lookup"><span data-stu-id="0ea0a-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea0a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ea0a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ea0a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ea0a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0ea0a-106">in Numero di processi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="0ea0a-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="0ea0a-107">out Puntatore alla matrice di oggetti [ICorPublishProcess](icorpublishprocess-interface.md) recuperati, ognuno dei quali rappresenta un processo.</span><span class="sxs-lookup"><span data-stu-id="0ea0a-107">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0ea0a-108">out Puntatore al numero di processi effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="0ea0a-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="0ea0a-109">Se `celt` è uno, questo valore può essere null.</span><span class="sxs-lookup"><span data-stu-id="0ea0a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ea0a-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0ea0a-110">Requirements</span></span>  
 <span data-ttu-id="0ea0a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ea0a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ea0a-112">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="0ea0a-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0ea0a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ea0a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ea0a-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ea0a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea0a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ea0a-115">See also</span></span>

- [<span data-ttu-id="0ea0a-116">Interfaccia ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="0ea0a-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)
