---
title: Funzione StrongNameHashSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameHashSize
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameHashSize
helpviewer_keywords: StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20a0d5fc284dde7b127f1f177a448a95701ac8b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="7b751-102">Funzione StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="7b751-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="7b751-103">Ottiene le dimensioni del buffer necessarie per generare un hash, utilizzando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="7b751-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="7b751-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="7b751-104">This function has been deprecated.</span></span> <span data-ttu-id="7b751-105">Utilizzare il [:: StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="7b751-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b751-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b751-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b751-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b751-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="7b751-108">[in] L'algoritmo hash utilizzato per calcolare le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="7b751-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="7b751-109">[out] Dimensioni del buffer restituito, in byte.</span><span class="sxs-lookup"><span data-stu-id="7b751-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b751-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7b751-110">Return Value</span></span>  
 <span data-ttu-id="7b751-111">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7b751-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b751-112">Note</span><span class="sxs-lookup"><span data-stu-id="7b751-112">Remarks</span></span>  
 <span data-ttu-id="7b751-113">Se il `StrongNameHashSize` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="7b751-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b751-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b751-114">Requirements</span></span>  
 <span data-ttu-id="7b751-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b751-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b751-116">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="7b751-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7b751-117">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b751-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b751-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b751-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b751-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b751-119">See Also</span></span>  
 [<span data-ttu-id="7b751-120">Metodo StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="7b751-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)  
 [<span data-ttu-id="7b751-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7b751-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
