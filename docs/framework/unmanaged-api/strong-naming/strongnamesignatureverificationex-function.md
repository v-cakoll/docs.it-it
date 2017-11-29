---
title: Funzione StrongNameSignatureVerificationEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationEx
helpviewer_keywords: StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0aebb53c6718a6812cbe6a6888f389c7b1a52dda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="1de56-102">Funzione StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="1de56-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="1de56-103">Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="1de56-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="1de56-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="1de56-104">This function has been deprecated.</span></span> <span data-ttu-id="1de56-105">Utilizzare il [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="1de56-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de56-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1de56-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1de56-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1de56-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="1de56-108">[in] Il percorso del file di (.exe o DLL) eseguibile portabile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="1de56-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="1de56-109">[in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1de56-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="1de56-110">[out] `true` se la firma nome sicuro è stato verificato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1de56-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="1de56-111">`pfWasVerified`viene inoltre impostata su `false` se la verifica ha esito positivo a causa delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="1de56-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1de56-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1de56-112">Return Value</span></span>  
 <span data-ttu-id="1de56-113">`true`Se la verifica ha avuto esito positivo. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1de56-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1de56-114">Note</span><span class="sxs-lookup"><span data-stu-id="1de56-114">Remarks</span></span>  
 <span data-ttu-id="1de56-115">`StrongNameSignatureVerificationEx`fornisce una funzionalità simile per la [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="1de56-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="1de56-116">Tuttavia, il secondo parametro di input e il parametro di output per `StrongNameSignatureVerificationEx` sono di tipo `BOOLEAN` anziché `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="1de56-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de56-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1de56-117">Requirements</span></span>  
 <span data-ttu-id="1de56-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1de56-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de56-119">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="1de56-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1de56-120">**Libreria:** inclusa come risorsa in mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1de56-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="1de56-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de56-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de56-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1de56-122">See Also</span></span>  
 [<span data-ttu-id="1de56-123">StrongNameSignatureVerificationEx (metodo)</span><span class="sxs-lookup"><span data-stu-id="1de56-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="1de56-124">StrongNameSignatureVerification (metodo)</span><span class="sxs-lookup"><span data-stu-id="1de56-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="1de56-125">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1de56-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
