---
title: Funzione StrongNameTokenFromAssemblyEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromAssemblyEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameTokenFromAssemblyEx
helpviewer_keywords: StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef530595d92995124c590e70ac5ffc32a228c67a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="4429d-102">Funzione StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="4429d-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="4429d-103">Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica che rappresenta il token.</span><span class="sxs-lookup"><span data-stu-id="4429d-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="4429d-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="4429d-104">This function has been deprecated.</span></span> <span data-ttu-id="4429d-105">Utilizzare il [ICLRStrongName:: StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="4429d-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4429d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4429d-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4429d-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="4429d-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4429d-108">[in] Il percorso del file eseguibile portabile (PE) per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="4429d-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="4429d-109">[out] Il token restituito con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4429d-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="4429d-110">[out] Le dimensioni in byte, del token con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4429d-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="4429d-111">[out] La chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="4429d-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="4429d-112">[out] Le dimensioni in byte, della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="4429d-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4429d-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4429d-113">Return Value</span></span>  
 <span data-ttu-id="4429d-114">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4429d-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4429d-115">Note</span><span class="sxs-lookup"><span data-stu-id="4429d-115">Remarks</span></span>  
 <span data-ttu-id="4429d-116">Un token con nome sicuro è la forma abbreviata di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="4429d-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="4429d-117">Il token è un hash a 64 bit che viene creato dalla chiave pubblica utilizzata per firmare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="4429d-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="4429d-118">Il token fa parte del nome sicuro per l'assembly e può essere letti dai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4429d-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="4429d-119">Dopo il recupero della chiave e il token viene creato, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) funzione per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="4429d-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="4429d-120">Se il `StrongNameTokenFromAssemblyEx` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="4429d-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4429d-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4429d-121">Requirements</span></span>  
 <span data-ttu-id="4429d-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4429d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4429d-123">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="4429d-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4429d-124">**Libreria:** inclusa come risorsa in mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4429d-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="4429d-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4429d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4429d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4429d-126">See Also</span></span>  
 [<span data-ttu-id="4429d-127">StrongNameTokenFromAssemblyEx (metodo)</span><span class="sxs-lookup"><span data-stu-id="4429d-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="4429d-128">StrongNameTokenFromAssembly (metodo)</span><span class="sxs-lookup"><span data-stu-id="4429d-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="4429d-129">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4429d-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
