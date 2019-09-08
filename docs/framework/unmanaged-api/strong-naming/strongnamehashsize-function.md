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
ms.openlocfilehash: 53384a5aa7f8d11f868057f892f7b60aac2e9f02
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799035"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="bb6f9-102">Funzione StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="bb6f9-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="bb6f9-103">Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="bb6f9-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="bb6f9-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="bb6f9-104">This function has been deprecated.</span></span> <span data-ttu-id="bb6f9-105">Usare invece il metodo [ICLRStrongName:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb6f9-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb6f9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb6f9-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb6f9-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb6f9-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="bb6f9-108">in Algoritmo hash utilizzato per calcolare le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="bb6f9-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="bb6f9-109">out Dimensioni del buffer restituito, in byte.</span><span class="sxs-lookup"><span data-stu-id="bb6f9-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb6f9-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bb6f9-110">Return Value</span></span>  
 <span data-ttu-id="bb6f9-111">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="bb6f9-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb6f9-112">Note</span><span class="sxs-lookup"><span data-stu-id="bb6f9-112">Remarks</span></span>  
 <span data-ttu-id="bb6f9-113">Se la `StrongNameHashSize` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="bb6f9-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb6f9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb6f9-114">Requirements</span></span>  
 <span data-ttu-id="bb6f9-115">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb6f9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb6f9-116">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="bb6f9-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bb6f9-117">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bb6f9-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb6f9-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb6f9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb6f9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb6f9-119">See also</span></span>

- [<span data-ttu-id="bb6f9-120">Metodo StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="bb6f9-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="bb6f9-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="bb6f9-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
