---
title: Metodo ICLRStrongName::StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de4e55c8e1a13daf07a8a75a19a44127779d5c05
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481612"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="4a1ee-102">Metodo ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="4a1ee-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="4a1ee-103">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4a1ee-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a1ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a1ee-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a1ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a1ee-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="4a1ee-106">[in] Il percorso dell'assembly prima.</span><span class="sxs-lookup"><span data-stu-id="4a1ee-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="4a1ee-107">[in] Il percorso dell'assembly di secondo.</span><span class="sxs-lookup"><span data-stu-id="4a1ee-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="4a1ee-108">[out] Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a1ee-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="4a1ee-109">`SN_CMP_DIFFERENT` (0): Specifica che gli assembly contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="4a1ee-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="4a1ee-110">`SN_CMP_IDENTICAL` (1): Specifica che gli assembly sono esattamente uguali, comprese le firme e checksum.</span><span class="sxs-lookup"><span data-stu-id="4a1ee-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="4a1ee-111">`SN_CMP_SIGONLY` (2): Specifica che gli assembly si differenziano solo per la firma e checksum.</span><span class="sxs-lookup"><span data-stu-id="4a1ee-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a1ee-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a1ee-112">Return Value</span></span>  
 <span data-ttu-id="4a1ee-113">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="4a1ee-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a1ee-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a1ee-114">Requirements</span></span>  
 <span data-ttu-id="4a1ee-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a1ee-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a1ee-116">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4a1ee-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4a1ee-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4a1ee-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a1ee-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a1ee-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a1ee-119">Note</span><span class="sxs-lookup"><span data-stu-id="4a1ee-119">Remarks</span></span>  
 <span data-ttu-id="4a1ee-120">La firma con nome sicuro di un assembly è costituito da testo Nome, versione, impostazioni cultura e token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a1ee-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a1ee-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a1ee-121">See also</span></span>
- [<span data-ttu-id="4a1ee-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="4a1ee-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
