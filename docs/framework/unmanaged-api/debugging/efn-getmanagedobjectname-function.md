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
ms.openlocfilehash: 9230e1fcba7c0492e50773e7ca13fb16f07238a2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789140"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="32c1b-102">\_AAPN\_funzione GetManagedObjectName</span><span class="sxs-lookup"><span data-stu-id="32c1b-102">\_EFN\_GetManagedObjectName Function</span></span>
<span data-ttu-id="32c1b-103">Ottiene il nome di un tipo utilizzando il puntatore all'oggetto gestito fornito.</span><span class="sxs-lookup"><span data-stu-id="32c1b-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c1b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32c1b-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32c1b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="32c1b-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="32c1b-106">in Puntatore al client di debug.</span><span class="sxs-lookup"><span data-stu-id="32c1b-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="32c1b-107">in Puntatore A un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="32c1b-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="32c1b-108">szName</span><span class="sxs-lookup"><span data-stu-id="32c1b-108">szName</span></span>  
 <span data-ttu-id="32c1b-109">out Nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="32c1b-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="32c1b-110">out Numero di caratteri disponibili nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="32c1b-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32c1b-111">Note</span><span class="sxs-lookup"><span data-stu-id="32c1b-111">Remarks</span></span>  
 <span data-ttu-id="32c1b-112">Se nel thread non è attualmente presente codice gestito, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore della funzione messaggi 0XA0 e un codice di errore 0x1000.</span><span class="sxs-lookup"><span data-stu-id="32c1b-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32c1b-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="32c1b-113">Requirements</span></span>  
 <span data-ttu-id="32c1b-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32c1b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32c1b-115">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="32c1b-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="32c1b-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32c1b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c1b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32c1b-117">See also</span></span>

- [<span data-ttu-id="32c1b-118">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="32c1b-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
