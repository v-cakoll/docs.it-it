---
title: Funzione StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd3813d977f94db4168da8c888485b323f4072ad
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471277"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="d2b57-102">Funzione StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="d2b57-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="d2b57-103">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d2b57-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="d2b57-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="d2b57-104">This function has been deprecated.</span></span> <span data-ttu-id="d2b57-105">Usare la [StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="d2b57-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b57-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2b57-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2b57-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2b57-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="d2b57-108">[in] Il percorso dell'assembly prima.</span><span class="sxs-lookup"><span data-stu-id="d2b57-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="d2b57-109">[in] Il percorso dell'assembly di secondo.</span><span class="sxs-lookup"><span data-stu-id="d2b57-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="d2b57-110">[out] Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2b57-110">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="d2b57-111">`SN_CMP_DIFFERENT` (0): Specifica che gli assembly contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="d2b57-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="d2b57-112">`SN_CMP_IDENTICAL` (1): Specifica che gli assembly sono esattamente uguali, comprese le firme e checksum.</span><span class="sxs-lookup"><span data-stu-id="d2b57-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="d2b57-113">`SN_CMP_SIGONLY` (2): Specifica che gli assembly si differenziano solo per la firma e checksum.</span><span class="sxs-lookup"><span data-stu-id="d2b57-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2b57-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d2b57-114">Return Value</span></span>  
 <span data-ttu-id="d2b57-115">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d2b57-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2b57-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2b57-116">Requirements</span></span>  
 <span data-ttu-id="d2b57-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2b57-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2b57-118">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d2b57-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d2b57-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d2b57-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2b57-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2b57-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2b57-121">Note</span><span class="sxs-lookup"><span data-stu-id="d2b57-121">Remarks</span></span>  
 <span data-ttu-id="d2b57-122">La firma con nome sicuro di un assembly è costituito da testo Nome, versione, impostazioni cultura e token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d2b57-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="d2b57-123">Se il `StrongNameCompareAssemblies` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="d2b57-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b57-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2b57-124">See also</span></span>
- [<span data-ttu-id="d2b57-125">Metodo StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="d2b57-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="d2b57-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d2b57-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
