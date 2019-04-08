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
ms.openlocfilehash: c7e807b502e0905f9ae785203289447c71d25e04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072145"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="fe714-102">Funzione StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="fe714-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="fe714-103">Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="fe714-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="fe714-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="fe714-104">This function has been deprecated.</span></span> <span data-ttu-id="fe714-105">Usare la [StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="fe714-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe714-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe714-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe714-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe714-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="fe714-108">[in] L'algoritmo hash usato per calcolare le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="fe714-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="fe714-109">[out] Dimensioni del buffer restituito, in byte.</span><span class="sxs-lookup"><span data-stu-id="fe714-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe714-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fe714-110">Return Value</span></span>  
 `true` <span data-ttu-id="fe714-111">al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="fe714-111">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe714-112">Note</span><span class="sxs-lookup"><span data-stu-id="fe714-112">Remarks</span></span>  
 <span data-ttu-id="fe714-113">Se il `StrongNameHashSize` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="fe714-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe714-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe714-114">Requirements</span></span>  
 <span data-ttu-id="fe714-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe714-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe714-116">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="fe714-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fe714-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fe714-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="fe714-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fe714-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fe714-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe714-119">See also</span></span>

- [<span data-ttu-id="fe714-120">Metodo StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="fe714-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="fe714-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="fe714-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
