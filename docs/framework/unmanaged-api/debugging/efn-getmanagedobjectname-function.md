---
title: Funzione _EFN_GetManagedObjectName
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3490477f30cd1c0badaa9cfd71433a5bf9d7a99
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738989"
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="f048d-102">\_EFN\_GetManagedObjectName (funzione)</span><span class="sxs-lookup"><span data-stu-id="f048d-102">\_EFN\_GetManagedObjectName Function</span></span>
<span data-ttu-id="f048d-103">Ottiene il nome di un tipo usando il puntatore all'oggetto gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="f048d-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f048d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f048d-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f048d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f048d-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="f048d-106">[in] Puntatore al client di debug.</span><span class="sxs-lookup"><span data-stu-id="f048d-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="f048d-107">[in] Un puntatore all'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="f048d-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="f048d-108">szName</span><span class="sxs-lookup"><span data-stu-id="f048d-108">szName</span></span>  
 <span data-ttu-id="f048d-109">[out] Il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="f048d-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="f048d-110">[out] Il numero di caratteri disponibili nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="f048d-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f048d-111">Note</span><span class="sxs-lookup"><span data-stu-id="f048d-111">Remarks</span></span>  
 <span data-ttu-id="f048d-112">Se non vi è nessun codice gestito sul thread attualmente nel contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore di impianto pari a 0xa0 e un codice di errore di 0x1000.</span><span class="sxs-lookup"><span data-stu-id="f048d-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f048d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f048d-113">Requirements</span></span>  
 <span data-ttu-id="f048d-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f048d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f048d-115">**Intestazione:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="f048d-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="f048d-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f048d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f048d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f048d-117">See also</span></span>

- [<span data-ttu-id="f048d-118">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="f048d-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
