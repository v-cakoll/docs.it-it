---
title: Funzione GetCORVersion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c61dd0b10bc0229d8f0d7dd4f6357ddaf5986637
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getcorversion-function"></a><span data-ttu-id="3ecb6-102">Funzione GetCORVersion</span><span class="sxs-lookup"><span data-stu-id="3ecb6-102">GetCORVersion Function</span></span>
<span data-ttu-id="3ecb6-103">Restituisce il numero di versione di common language runtime (CLR) che è in esecuzione nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="3ecb6-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="3ecb6-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ecb6-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ecb6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ecb6-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ecb6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ecb6-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="3ecb6-107">Un puntatore a un buffer in cui CLR restituisce una stringa che specifica la versione del runtime attualmente caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="3ecb6-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="3ecb6-108">La stringa restituita assume lo stesso formato passata a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), ad esempio, "v 1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="3ecb6-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="3ecb6-109">Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriata per la versione più recente del runtime installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="3ecb6-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="3ecb6-110">Il numero di caratteri (`WCHAR`s) che possono essere contenuti in `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="3ecb6-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="3ecb6-111">Un puntatore al numero di caratteri effettivamente restituiti in `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="3ecb6-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="3ecb6-112">Se `pbuffer` è un puntatore null, il runtime restituisce E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="3ecb6-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="3ecb6-113">Se il numero di caratteri è maggiore della lunghezza della `pbuffer` , viene restituito ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="3ecb6-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ecb6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ecb6-114">Requirements</span></span>  
 <span data-ttu-id="3ecb6-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ecb6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ecb6-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3ecb6-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ecb6-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ecb6-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ecb6-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ecb6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ecb6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ecb6-119">See Also</span></span>  
 [<span data-ttu-id="3ecb6-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="3ecb6-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
