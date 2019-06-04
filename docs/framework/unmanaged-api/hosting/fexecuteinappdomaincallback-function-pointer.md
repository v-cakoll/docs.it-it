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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26b3de456bc28f51cb20ab72b3934041ec6b06ae
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490448"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="09e48-102">Puntatore alla funzione FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="09e48-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="09e48-103">Punta a una funzione che viene chiamato da common language runtime (CLR) per eseguire il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="09e48-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="09e48-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="09e48-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e48-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09e48-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09e48-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="09e48-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="09e48-107">[in] Puntatore alla memoria allocata dal chiamante opaco che contiene il codice gestito deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="09e48-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="09e48-108">La durata della memoria e allocazione sono controllate dal chiamante (vale a dire, Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="09e48-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="09e48-109">Non si tratta della memoria heap gestito CLR.</span><span class="sxs-lookup"><span data-stu-id="09e48-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09e48-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09e48-110">Requirements</span></span>  
 <span data-ttu-id="09e48-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09e48-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09e48-112">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="09e48-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09e48-113">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="09e48-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="09e48-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09e48-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e48-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09e48-115">See also</span></span>

- [<span data-ttu-id="09e48-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="09e48-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
