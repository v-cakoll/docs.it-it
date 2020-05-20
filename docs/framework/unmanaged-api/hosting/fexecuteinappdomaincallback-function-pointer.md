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
ms.openlocfilehash: 6fd7a19d9fc77b43bbceb1b5e5399a455429e700
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616151"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="e8c94-102">Puntatore alla funzione FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="e8c94-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="e8c94-103">Punta a una funzione chiamata dall'Common Language Runtime (CLR) per eseguire codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e8c94-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="e8c94-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e8c94-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8c94-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8c94-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8c94-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8c94-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="e8c94-107">in Puntatore alla memoria allocata dal chiamante opaco che contiene il codice gestito da eseguire.</span><span class="sxs-lookup"><span data-stu-id="e8c94-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="e8c94-108">L'allocazione e la durata della memoria sono controllate dal chiamante (ovvero CLR).</span><span class="sxs-lookup"><span data-stu-id="e8c94-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="e8c94-109">Non si tratta di una memoria heap gestita da CLR.</span><span class="sxs-lookup"><span data-stu-id="e8c94-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8c94-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8c94-110">Requirements</span></span>  
 <span data-ttu-id="e8c94-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8c94-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8c94-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e8c94-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8c94-113">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="e8c94-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="e8c94-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8c94-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c94-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8c94-115">See also</span></span>

- [<span data-ttu-id="e8c94-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="e8c94-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
