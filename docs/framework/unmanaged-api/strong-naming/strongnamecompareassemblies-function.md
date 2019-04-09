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
ms.openlocfilehash: 2a49252d00f75b4d0b6325aeae0aab22f8ada5e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191380"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="bdbea-102">Funzione StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="bdbea-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="bdbea-103">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="bdbea-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="bdbea-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="bdbea-104">This function has been deprecated.</span></span> <span data-ttu-id="bdbea-105">Usare la [StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="bdbea-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdbea-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdbea-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdbea-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="bdbea-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="bdbea-108">[in] Il percorso dell'assembly prima.</span><span class="sxs-lookup"><span data-stu-id="bdbea-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="bdbea-109">[in] Il percorso dell'assembly di secondo.</span><span class="sxs-lookup"><span data-stu-id="bdbea-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="bdbea-110">[out] Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="bdbea-110">[out] One of the following values:</span></span>  
  
-   `SN_CMP_DIFFERENT` <span data-ttu-id="bdbea-111">(0): Specifica che gli assembly contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="bdbea-111">(0) - Specifies that the assemblies contain different data.</span></span>  
  
-   `SN_CMP_IDENTICAL` <span data-ttu-id="bdbea-112">(1): Specifica che gli assembly sono esattamente uguali, comprese le firme e checksum.</span><span class="sxs-lookup"><span data-stu-id="bdbea-112">(1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   `SN_CMP_SIGONLY` <span data-ttu-id="bdbea-113">(2): Specifica che gli assembly si differenziano solo per la firma e checksum.</span><span class="sxs-lookup"><span data-stu-id="bdbea-113">(2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdbea-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bdbea-114">Return Value</span></span>  
 `true` <span data-ttu-id="bdbea-115">al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="bdbea-115">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdbea-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bdbea-116">Requirements</span></span>  
 <span data-ttu-id="bdbea-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdbea-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdbea-118">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bdbea-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bdbea-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bdbea-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="bdbea-120">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bdbea-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="bdbea-121">Note</span><span class="sxs-lookup"><span data-stu-id="bdbea-121">Remarks</span></span>  
 <span data-ttu-id="bdbea-122">La firma con nome sicuro di un assembly è costituito da testo Nome, versione, impostazioni cultura e token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bdbea-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="bdbea-123">Se il `StrongNameCompareAssemblies` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="bdbea-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdbea-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdbea-124">See also</span></span>

- [<span data-ttu-id="bdbea-125">Metodo StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="bdbea-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="bdbea-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="bdbea-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
