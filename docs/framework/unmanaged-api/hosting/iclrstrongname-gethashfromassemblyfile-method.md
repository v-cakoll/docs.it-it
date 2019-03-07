---
title: Metodo ICLRStrongName::GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11e45e5a834c27f825db3419b2d8675f9a9a37d5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493414"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="09b39-102">Metodo ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="09b39-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="09b39-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="09b39-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09b39-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09b39-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09b39-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="09b39-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="09b39-106">[in] Il percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="09b39-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="09b39-107">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="09b39-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="09b39-108">Usa lo zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="09b39-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="09b39-109">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="09b39-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="09b39-110">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="09b39-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="09b39-111">[out] La dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="09b39-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09b39-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="09b39-112">Return Value</span></span>  
 <span data-ttu-id="09b39-113">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="09b39-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09b39-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09b39-114">Requirements</span></span>  
 <span data-ttu-id="09b39-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09b39-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09b39-116">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="09b39-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="09b39-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="09b39-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09b39-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09b39-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b39-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09b39-119">See also</span></span>
- [<span data-ttu-id="09b39-120">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="09b39-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="09b39-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="09b39-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
