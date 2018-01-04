---
title: Funzione StrongNameCompareAssemblies
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameCompareAssemblies
helpviewer_keywords: StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ed98b1713427a71c73c30ddd64188f61d51045c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="19831-102">Funzione StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="19831-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="19831-103">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="19831-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="19831-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="19831-104">This function has been deprecated.</span></span> <span data-ttu-id="19831-105">Utilizzare il [:: StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="19831-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19831-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19831-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19831-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="19831-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="19831-108">[in] Il percorso del primo assembly.</span><span class="sxs-lookup"><span data-stu-id="19831-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="19831-109">[in] Il percorso per il secondo assembly.</span><span class="sxs-lookup"><span data-stu-id="19831-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="19831-110">[out] Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="19831-110">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="19831-111">`SN_CMP_DIFFERENT`(0): Specifica che l'assembly deve contenere dati diversi.</span><span class="sxs-lookup"><span data-stu-id="19831-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="19831-112">`SN_CMP_IDENTICAL`(1) - specifica che gli assembly sono esattamente uguali, comprese le firme e checksum.</span><span class="sxs-lookup"><span data-stu-id="19831-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="19831-113">`SN_CMP_SIGONLY`(2) - specifica che gli assembly si differenziano solo per la firma e checksum.</span><span class="sxs-lookup"><span data-stu-id="19831-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19831-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="19831-114">Return Value</span></span>  
 <span data-ttu-id="19831-115">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="19831-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19831-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19831-116">Requirements</span></span>  
 <span data-ttu-id="19831-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19831-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19831-118">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="19831-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="19831-119">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19831-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19831-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19831-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19831-121">Note</span><span class="sxs-lookup"><span data-stu-id="19831-121">Remarks</span></span>  
 <span data-ttu-id="19831-122">La firma nome sicuro di un assembly è costituito da testo Nome, versione, impostazioni cultura e token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="19831-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="19831-123">Se il `StrongNameCompareAssemblies` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="19831-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19831-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19831-124">See Also</span></span>  
 [<span data-ttu-id="19831-125">Metodo StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="19831-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)  
 [<span data-ttu-id="19831-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="19831-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
