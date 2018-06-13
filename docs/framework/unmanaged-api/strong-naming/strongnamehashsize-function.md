---
title: Funzione StrongNameHashSize
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92b9d9b5baee856f09dd24a62767aff604728997
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454082"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="7d340-102">Funzione StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="7d340-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="7d340-103">Ottiene le dimensioni del buffer necessarie per generare un hash, utilizzando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="7d340-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="7d340-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="7d340-104">This function has been deprecated.</span></span> <span data-ttu-id="7d340-105">Utilizzare il [:: StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="7d340-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d340-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d340-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d340-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="7d340-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="7d340-108">[in] L'algoritmo hash utilizzato per calcolare le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="7d340-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="7d340-109">[out] Dimensioni del buffer restituito, in byte.</span><span class="sxs-lookup"><span data-stu-id="7d340-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d340-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7d340-110">Return Value</span></span>  
 <span data-ttu-id="7d340-111">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7d340-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d340-112">Note</span><span class="sxs-lookup"><span data-stu-id="7d340-112">Remarks</span></span>  
 <span data-ttu-id="7d340-113">Se il `StrongNameHashSize` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="7d340-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d340-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d340-114">Requirements</span></span>  
 <span data-ttu-id="7d340-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d340-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d340-116">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="7d340-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7d340-117">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7d340-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d340-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d340-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d340-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d340-119">See Also</span></span>  
 [<span data-ttu-id="7d340-120">Metodo StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="7d340-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)  
 [<span data-ttu-id="7d340-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7d340-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
