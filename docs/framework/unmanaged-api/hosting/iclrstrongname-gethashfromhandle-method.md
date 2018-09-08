---
title: Metodo ICLRStrongName::GetHashFromHandle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20c5f6bbb58b85f42ec00e356eccc5fb41ce813c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199570"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="65af5-102">Metodo ICLRStrongName::GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="65af5-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="65af5-103">Genera un hash per il contenuto del file che contiene l'handle di file specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="65af5-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65af5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65af5-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65af5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65af5-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="65af5-106">[in] L'handle del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="65af5-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="65af5-107">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="65af5-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="65af5-108">Usa lo zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="65af5-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="65af5-109">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="65af5-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="65af5-110">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="65af5-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="65af5-111">[out] Le dimensioni, in byte, del valore restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="65af5-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65af5-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="65af5-112">Return Value</span></span>  
 <span data-ttu-id="65af5-113">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="65af5-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65af5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65af5-114">Requirements</span></span>  
 <span data-ttu-id="65af5-115">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65af5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65af5-116">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="65af5-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="65af5-117">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="65af5-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65af5-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65af5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65af5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65af5-119">See Also</span></span>  
 [<span data-ttu-id="65af5-120">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="65af5-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
