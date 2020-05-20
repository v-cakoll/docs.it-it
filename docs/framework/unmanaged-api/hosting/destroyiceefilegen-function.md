---
title: Funzione DestroyICeeFileGen
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: ff7e7b299d185b8db263d2076c1e075b87b487fc
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616398"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="43e0a-102">Funzione DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="43e0a-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="43e0a-103">Elimina definitivamente un oggetto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="43e0a-103">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="43e0a-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="43e0a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e0a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43e0a-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43e0a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="43e0a-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="43e0a-107">in `ICeeFileGen`Oggetto da eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="43e0a-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43e0a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="43e0a-108">Return Value</span></span>  
 <span data-ttu-id="43e0a-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="43e0a-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43e0a-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="43e0a-110">Remarks</span></span>  
 <span data-ttu-id="43e0a-111">`DestroyICeeFileGen`Elimina definitivamente l' `ICeeFileGen` oggetto creato dalla funzione [CreateICeeFileGen](createiceefilegen-function.md) .</span><span class="sxs-lookup"><span data-stu-id="43e0a-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e0a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43e0a-112">Requirements</span></span>  
 <span data-ttu-id="43e0a-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43e0a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43e0a-114">**Intestazione:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="43e0a-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="43e0a-115">**Libreria:** MSCorPE. dll</span><span class="sxs-lookup"><span data-stu-id="43e0a-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="43e0a-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43e0a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e0a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43e0a-117">See also</span></span>

- [<span data-ttu-id="43e0a-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="43e0a-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
