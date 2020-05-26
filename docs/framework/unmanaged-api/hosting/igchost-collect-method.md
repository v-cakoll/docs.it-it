---
title: Metodo IGCHost::Collect
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
ms.openlocfilehash: ac73c462aa210927f0665cae161fd7f3e17a0cdb
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805303"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="26a86-102">Metodo IGCHost::Collect</span><span class="sxs-lookup"><span data-stu-id="26a86-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="26a86-103">Impone l'esecuzione di una raccolta per la generazione specificata, indipendentemente dallo stato della Garbage Collection corrente.</span><span class="sxs-lookup"><span data-stu-id="26a86-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26a86-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26a86-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26a86-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="26a86-106">in Generazione sulla quale eseguire il Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="26a86-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="26a86-107">Il valore-1 indica che tutte le generazioni subiranno un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="26a86-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26a86-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26a86-108">Requirements</span></span>  
 <span data-ttu-id="26a86-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26a86-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26a86-110">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="26a86-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="26a86-111">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="26a86-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26a86-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26a86-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a86-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26a86-113">See also</span></span>

- [<span data-ttu-id="26a86-114">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="26a86-114">IGCHost Interface</span></span>](igchost-interface.md)
