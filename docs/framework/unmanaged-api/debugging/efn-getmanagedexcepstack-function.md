---
title: Funzione _EFN_GetManagedExcepStack
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedExcepStack
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedExcepStack
helpviewer_keywords: _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9dabcf1d39bea44a3bd90824082a082ae9650b54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="6da02-102">Funzione _EFN_GetManagedExcepStack</span><span class="sxs-lookup"><span data-stu-id="6da02-102">_EFN_GetManagedExcepStack Function</span></span>
<span data-ttu-id="6da02-103">Restituisce una versione stringa della traccia dello stack contenuta internamente, dato l'indirizzo di un oggetto eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="6da02-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6da02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6da02-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6da02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6da02-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="6da02-106">[in] Il client è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="6da02-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="6da02-107">[in] Puntatore a un oggetto gestito, derivato da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="6da02-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="6da02-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="6da02-108">szStackString</span></span>  
 <span data-ttu-id="6da02-109">[out] La stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="6da02-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="6da02-110">[out] Il numero di caratteri disponibili nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="6da02-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6da02-111">Note</span><span class="sxs-lookup"><span data-stu-id="6da02-111">Remarks</span></span>  
 <span data-ttu-id="6da02-112">Se non è presente nessun codice gestito sul thread attualmente in contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore funzionalità 0xa0 e un codice di errore di 0x1000.</span><span class="sxs-lookup"><span data-stu-id="6da02-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6da02-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6da02-113">Requirements</span></span>  
 <span data-ttu-id="6da02-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6da02-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6da02-115">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="6da02-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="6da02-116">**Versione di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6da02-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6da02-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6da02-117">See Also</span></span>  
 [<span data-ttu-id="6da02-118">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="6da02-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
