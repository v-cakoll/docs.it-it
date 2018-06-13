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
ms.openlocfilehash: c5020c31f590f527856f966ede512e98c07496ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435388"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="bac14-102">Metodo ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="bac14-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="bac14-103">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="bac14-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bac14-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bac14-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bac14-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="bac14-106">[in] Il percorso del primo assembly.</span><span class="sxs-lookup"><span data-stu-id="bac14-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="bac14-107">[in] Il percorso per il secondo assembly.</span><span class="sxs-lookup"><span data-stu-id="bac14-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="bac14-108">[out] Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="bac14-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="bac14-109">`SN_CMP_DIFFERENT` (0): Specifica che l'assembly deve contenere dati diversi.</span><span class="sxs-lookup"><span data-stu-id="bac14-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="bac14-110">`SN_CMP_IDENTICAL` (1) - specifica che gli assembly sono esattamente uguali, comprese le firme e checksum.</span><span class="sxs-lookup"><span data-stu-id="bac14-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="bac14-111">`SN_CMP_SIGONLY` (2) - specifica che gli assembly si differenziano solo per la firma e checksum.</span><span class="sxs-lookup"><span data-stu-id="bac14-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bac14-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bac14-112">Return Value</span></span>  
 <span data-ttu-id="bac14-113">`S_OK` Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="bac14-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bac14-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bac14-114">Requirements</span></span>  
 <span data-ttu-id="bac14-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bac14-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bac14-116">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="bac14-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bac14-117">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bac14-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bac14-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bac14-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bac14-119">Note</span><span class="sxs-lookup"><span data-stu-id="bac14-119">Remarks</span></span>  
 <span data-ttu-id="bac14-120">La firma nome sicuro di un assembly è costituito da testo Nome, versione, impostazioni cultura e token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bac14-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac14-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bac14-121">See Also</span></span>  
 [<span data-ttu-id="bac14-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="bac14-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
