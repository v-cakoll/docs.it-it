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
ms.openlocfilehash: c656f73748faf8be7124be65f3ed455f2d5fd07a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105181"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="2805b-102">Funzione StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="2805b-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="2805b-103">Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="2805b-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="2805b-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="2805b-104">This function has been deprecated.</span></span> <span data-ttu-id="2805b-105">Usare invece il metodo [ICLRStrongName:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2805b-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2805b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2805b-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2805b-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="2805b-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="2805b-108">in Algoritmo hash utilizzato per calcolare le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="2805b-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="2805b-109">out Dimensioni del buffer restituito, in byte.</span><span class="sxs-lookup"><span data-stu-id="2805b-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2805b-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2805b-110">Return Value</span></span>  
 <span data-ttu-id="2805b-111">`true` al completamento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2805b-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2805b-112">Note</span><span class="sxs-lookup"><span data-stu-id="2805b-112">Remarks</span></span>  
 <span data-ttu-id="2805b-113">Se la funzione `StrongNameHashSize` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="2805b-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2805b-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2805b-114">Requirements</span></span>  
 <span data-ttu-id="2805b-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2805b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2805b-116">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="2805b-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2805b-117">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2805b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2805b-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2805b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2805b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2805b-119">See also</span></span>

- [<span data-ttu-id="2805b-120">Metodo StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="2805b-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="2805b-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="2805b-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
