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
ms.openlocfilehash: 6d11c71498053844792cd902959dee642877c46b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146978"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="094d8-102">Metodo ICLRStrongName::GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="094d8-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="094d8-103">Genera un hash per il contenuto del file che contiene l'handle di file specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="094d8-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="094d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="094d8-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="094d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="094d8-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="094d8-106">[in] L'handle del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="094d8-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="094d8-107">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="094d8-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="094d8-108">Usa lo zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="094d8-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="094d8-109">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="094d8-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="094d8-110">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="094d8-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="094d8-111">[out] Le dimensioni, in byte, del valore restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="094d8-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="094d8-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="094d8-112">Return Value</span></span>  
 <span data-ttu-id="094d8-113">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="094d8-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="094d8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="094d8-114">Requirements</span></span>  
 <span data-ttu-id="094d8-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="094d8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="094d8-116">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="094d8-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="094d8-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="094d8-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="094d8-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="094d8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="094d8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="094d8-119">See also</span></span>

- [<span data-ttu-id="094d8-120">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="094d8-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
