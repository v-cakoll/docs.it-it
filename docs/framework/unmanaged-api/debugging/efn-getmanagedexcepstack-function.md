---
title: Funzione _EFN_GetManagedExcepStack
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
ms.openlocfilehash: c50fe09648793ba7340960654811ff31187269d8
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860795"
---
# <a name="_efn_getmanagedexcepstack-function"></a><span data-ttu-id="fb08d-102">\_AAPN\_GetManagedExcepStack-funzione</span><span class="sxs-lookup"><span data-stu-id="fb08d-102">\_EFN\_GetManagedExcepStack Function</span></span>
<span data-ttu-id="fb08d-103">Restituisce una versione stringa della traccia dello stack contenuta internamente, dato l'indirizzo di un oggetto eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="fb08d-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb08d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb08d-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb08d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fb08d-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="fb08d-106">in Client di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="fb08d-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="fb08d-107">in Puntatore a un oggetto gestito, derivato <xref:System.Exception>da.</span><span class="sxs-lookup"><span data-stu-id="fb08d-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="fb08d-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="fb08d-108">szStackString</span></span>  
 <span data-ttu-id="fb08d-109">out Stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="fb08d-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="fb08d-110">out Numero di caratteri disponibili nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="fb08d-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb08d-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fb08d-111">Remarks</span></span>  
 <span data-ttu-id="fb08d-112">Se nel thread non è attualmente presente codice gestito, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore della funzione messaggi 0XA0 e un codice di errore 0x1000.</span><span class="sxs-lookup"><span data-stu-id="fb08d-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb08d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fb08d-113">Requirements</span></span>  
 <span data-ttu-id="fb08d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb08d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb08d-115">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="fb08d-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="fb08d-116">**Versione .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb08d-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb08d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb08d-117">See also</span></span>

- [<span data-ttu-id="fb08d-118">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="fb08d-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
