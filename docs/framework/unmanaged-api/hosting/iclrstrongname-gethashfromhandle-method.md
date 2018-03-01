---
title: Metodo ICLRStrongName::GetHashFromHandle
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
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 61e0f0cc5ba4bb48f5d54427f6e94f72ef8fbd00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="da1e9-102">Metodo ICLRStrongName::GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="da1e9-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="da1e9-103">Genera un hash per il contenuto del file che contiene l'handle di file specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="da1e9-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da1e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da1e9-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da1e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da1e9-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="da1e9-106">[in] L'handle del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="da1e9-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="da1e9-107">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="da1e9-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="da1e9-108">Utilizzare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="da1e9-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="da1e9-109">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="da1e9-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="da1e9-110">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="da1e9-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="da1e9-111">[out] Le dimensioni, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="da1e9-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da1e9-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="da1e9-112">Return Value</span></span>  
 <span data-ttu-id="da1e9-113">`S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="da1e9-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da1e9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da1e9-114">Requirements</span></span>  
 <span data-ttu-id="da1e9-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da1e9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da1e9-116">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="da1e9-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="da1e9-117">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da1e9-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da1e9-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da1e9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da1e9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da1e9-119">See Also</span></span>  
 [<span data-ttu-id="da1e9-120">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="da1e9-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
