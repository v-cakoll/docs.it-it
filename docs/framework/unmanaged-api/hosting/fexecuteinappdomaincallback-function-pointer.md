---
title: Puntatore alla funzione FExecuteInAppDomainCallback
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
ms.openlocfilehash: 970468bc2f50144c62c6e3cbcf9c00c2027f7663
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138174"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="9317c-102">Puntatore alla funzione FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="9317c-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="9317c-103">Punta a una funzione chiamata dall'Common Language Runtime (CLR) per eseguire codice gestito.</span><span class="sxs-lookup"><span data-stu-id="9317c-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="9317c-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9317c-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9317c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9317c-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9317c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9317c-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="9317c-107">in Puntatore alla memoria allocata dal chiamante opaco che contiene il codice gestito da eseguire.</span><span class="sxs-lookup"><span data-stu-id="9317c-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="9317c-108">L'allocazione e la durata della memoria sono controllate dal chiamante (ovvero CLR).</span><span class="sxs-lookup"><span data-stu-id="9317c-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="9317c-109">Non si tratta di una memoria heap gestita da CLR.</span><span class="sxs-lookup"><span data-stu-id="9317c-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9317c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9317c-110">Requirements</span></span>  
 <span data-ttu-id="9317c-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9317c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9317c-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9317c-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9317c-113">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="9317c-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="9317c-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9317c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9317c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9317c-115">See also</span></span>

- [<span data-ttu-id="9317c-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="9317c-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
