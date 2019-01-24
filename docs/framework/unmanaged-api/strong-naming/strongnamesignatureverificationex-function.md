---
title: Funzione StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9887a05236b213fb439e334cdf1455f8f445e7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671928"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="284bc-102">Funzione StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="284bc-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="284bc-103">Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="284bc-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="284bc-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="284bc-104">This function has been deprecated.</span></span> <span data-ttu-id="284bc-105">Usare la [StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="284bc-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="284bc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="284bc-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="284bc-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="284bc-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="284bc-108">[in] Il percorso del file di (.exe o DLL) eseguibile portabile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="284bc-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="284bc-109">[in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="284bc-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="284bc-110">[out] `true` se la firma con nome sicuro è stato verificato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="284bc-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="284bc-111">`pfWasVerified` viene inoltre impostata su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="284bc-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="284bc-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="284bc-112">Return Value</span></span>  
 <span data-ttu-id="284bc-113">`true` Se la verifica ha avuto esito positivo. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="284bc-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="284bc-114">Note</span><span class="sxs-lookup"><span data-stu-id="284bc-114">Remarks</span></span>  
 <span data-ttu-id="284bc-115">`StrongNameSignatureVerificationEx` fornisce una funzionalità simile per il [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="284bc-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="284bc-116">Tuttavia, il secondo parametro di input e il parametro di output per `StrongNameSignatureVerificationEx` sono di tipo `BOOLEAN` invece di `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="284bc-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="284bc-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="284bc-117">Requirements</span></span>  
 <span data-ttu-id="284bc-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="284bc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="284bc-119">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="284bc-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="284bc-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="284bc-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="284bc-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="284bc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="284bc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="284bc-122">See also</span></span>
- [<span data-ttu-id="284bc-123">Metodo StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="284bc-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="284bc-124">Metodo StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="284bc-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="284bc-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="284bc-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
