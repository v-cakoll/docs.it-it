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
ms.openlocfilehash: c7333f8f7b95655ac821e9a2977d5db3794486a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122998"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="39c4f-102">\_AAPN\_funzione GetManagedObjectName</span><span class="sxs-lookup"><span data-stu-id="39c4f-102">\_EFN\_GetManagedObjectName Function</span></span>
<span data-ttu-id="39c4f-103">Ottiene il nome di un tipo utilizzando il puntatore all'oggetto gestito fornito.</span><span class="sxs-lookup"><span data-stu-id="39c4f-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c4f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39c4f-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39c4f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="39c4f-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="39c4f-106">in Puntatore al client di debug.</span><span class="sxs-lookup"><span data-stu-id="39c4f-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="39c4f-107">in Puntatore A un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="39c4f-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="39c4f-108">szName</span><span class="sxs-lookup"><span data-stu-id="39c4f-108">szName</span></span>  
 <span data-ttu-id="39c4f-109">out Nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="39c4f-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="39c4f-110">out Numero di caratteri disponibili nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="39c4f-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39c4f-111">Note</span><span class="sxs-lookup"><span data-stu-id="39c4f-111">Remarks</span></span>  
 <span data-ttu-id="39c4f-112">Se nel thread non è attualmente presente codice gestito nel contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con il valore della funzione messaggi 0XA0 e un codice di errore 0x1000.</span><span class="sxs-lookup"><span data-stu-id="39c4f-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c4f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39c4f-113">Requirements</span></span>  
 <span data-ttu-id="39c4f-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39c4f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c4f-115">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="39c4f-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="39c4f-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39c4f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c4f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39c4f-117">See also</span></span>

- [<span data-ttu-id="39c4f-118">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="39c4f-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
