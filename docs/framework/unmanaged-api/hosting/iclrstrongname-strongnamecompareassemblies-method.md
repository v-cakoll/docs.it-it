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
ms.openlocfilehash: 63d4b885b6968b800bc965a9be1ec6b795a42220
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140660"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="b6fce-102">Metodo ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="b6fce-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="b6fce-103">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b6fce-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6fce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6fce-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6fce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6fce-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="b6fce-106">[in] Il percorso dell'assembly prima.</span><span class="sxs-lookup"><span data-stu-id="b6fce-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="b6fce-107">[in] Il percorso dell'assembly di secondo.</span><span class="sxs-lookup"><span data-stu-id="b6fce-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="b6fce-108">[out] Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6fce-108">[out] One of the following values:</span></span>  
  
-   `SN_CMP_DIFFERENT` <span data-ttu-id="b6fce-109">(0): Specifica che gli assembly contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="b6fce-109">(0) - Specifies that the assemblies contain different data.</span></span>  
  
-   `SN_CMP_IDENTICAL` <span data-ttu-id="b6fce-110">(1): Specifica che gli assembly sono esattamente uguali, comprese le firme e checksum.</span><span class="sxs-lookup"><span data-stu-id="b6fce-110">(1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   `SN_CMP_SIGONLY` <span data-ttu-id="b6fce-111">(2): Specifica che gli assembly si differenziano solo per la firma e checksum.</span><span class="sxs-lookup"><span data-stu-id="b6fce-111">(2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6fce-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b6fce-112">Return Value</span></span>  
 `S_OK` <span data-ttu-id="b6fce-113">Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="b6fce-113">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6fce-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6fce-114">Requirements</span></span>  
 <span data-ttu-id="b6fce-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6fce-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6fce-116">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b6fce-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b6fce-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b6fce-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b6fce-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b6fce-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="b6fce-119">Note</span><span class="sxs-lookup"><span data-stu-id="b6fce-119">Remarks</span></span>  
 <span data-ttu-id="b6fce-120">La firma con nome sicuro di un assembly è costituito da testo Nome, versione, impostazioni cultura e token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b6fce-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6fce-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6fce-121">See also</span></span>

- [<span data-ttu-id="b6fce-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b6fce-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
