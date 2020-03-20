---
title: Metodo ICorPublishAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: 6f7f400c51ded0b98c0c2286cb6f90bbd77e47d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178404"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="23d74-102">Metodo ICorPublishAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="23d74-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="23d74-103">Ottiene il numero specificato di domini applicazione attualmente presenti nel processo, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="23d74-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23d74-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23d74-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="23d74-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="23d74-106">[in] Numero di elementi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="23d74-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="23d74-107">[fuori] Puntatore alla matrice di oggetti [ICorPublishAppDomain](icorpublishappdomain-interface.md) recuperati, ognuno dei quali rappresenta un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="23d74-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="23d74-108">[fuori] Puntatore al numero di domini applicazione effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="23d74-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="23d74-109">Questo valore può `celt` essere null se è uno.</span><span class="sxs-lookup"><span data-stu-id="23d74-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23d74-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23d74-110">Requirements</span></span>  
 <span data-ttu-id="23d74-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23d74-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23d74-112">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="23d74-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="23d74-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23d74-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23d74-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23d74-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d74-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23d74-115">See also</span></span>

- [<span data-ttu-id="23d74-116">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="23d74-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
