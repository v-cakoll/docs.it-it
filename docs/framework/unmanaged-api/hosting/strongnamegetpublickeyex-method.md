---
title: Metodo StrongNameGetPublicKeyEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameGetPublicKeyEx
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f39c5c948d43fd0e9387c1cc0319a46d25ec86ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="513d6-102">Metodo StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="513d6-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="513d6-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="513d6-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="513d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="513d6-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="513d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="513d6-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="513d6-106">[in] Il nome del contenitore di chiavi contenente la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="513d6-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="513d6-107">Se `pbKeyBlob` è null, `szKeyContainer` deve specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="513d6-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="513d6-108">In questo caso, il `StrongNameGetPublicKeyEx` metodo estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="513d6-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="513d6-109">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().</span><span class="sxs-lookup"><span data-stu-id="513d6-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="513d6-110">Le chiavi devono essere Rivest-Shamir-Adleman (RSA a 1024 bit) le chiavi di firma.</span><span class="sxs-lookup"><span data-stu-id="513d6-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="513d6-111">Nessun altro tipo di chiavi è supportato in questo momento.</span><span class="sxs-lookup"><span data-stu-id="513d6-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="513d6-112">[in] Un puntatore per la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="513d6-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="513d6-113">Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione).</span><span class="sxs-lookup"><span data-stu-id="513d6-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="513d6-114">Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `szKeyContainer` si presuppone che la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="513d6-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="513d6-115">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="513d6-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="513d6-116">[out] Chiave pubblica restituita BLOB.</span><span class="sxs-lookup"><span data-stu-id="513d6-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="513d6-117">Il `ppbPublicKeyBlob` parametro è allocata da common language runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="513d6-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="513d6-118">Il chiamante deve liberare la memoria utilizzando il [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="513d6-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="513d6-119">[out] Le dimensioni della chiave pubblica restituita BLOB.</span><span class="sxs-lookup"><span data-stu-id="513d6-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="513d6-120">[in] L'algoritmo di hash di assembly.</span><span class="sxs-lookup"><span data-stu-id="513d6-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="513d6-121">Vedere la sezione Osservazioni per un elenco di valori accettati.</span><span class="sxs-lookup"><span data-stu-id="513d6-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="513d6-122">[in] Riservato per utilizzi futuri; valore predefinito è null.</span><span class="sxs-lookup"><span data-stu-id="513d6-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="513d6-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="513d6-123">Return Value</span></span>  
 <span data-ttu-id="513d6-124">`S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="513d6-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="513d6-125">Note</span><span class="sxs-lookup"><span data-stu-id="513d6-125">Remarks</span></span>  
 <span data-ttu-id="513d6-126">La chiave pubblica è contenuta un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="513d6-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="513d6-127">Note</span><span class="sxs-lookup"><span data-stu-id="513d6-127">Remarks</span></span>  
 <span data-ttu-id="513d6-128">Nella tabella seguente mostra il set di valori accettati per il `uHashAlgId` parametro.</span><span class="sxs-lookup"><span data-stu-id="513d6-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="513d6-129">Nome</span><span class="sxs-lookup"><span data-stu-id="513d6-129">Name</span></span>|<span data-ttu-id="513d6-130">Valore</span><span class="sxs-lookup"><span data-stu-id="513d6-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="513d6-131">None</span><span class="sxs-lookup"><span data-stu-id="513d6-131">None</span></span>|<span data-ttu-id="513d6-132">0</span><span class="sxs-lookup"><span data-stu-id="513d6-132">0</span></span>|  
|<span data-ttu-id="513d6-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="513d6-133">SHA-1</span></span>|<span data-ttu-id="513d6-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="513d6-134">0x8004</span></span>|  
|<span data-ttu-id="513d6-135">SHA-256.</span><span class="sxs-lookup"><span data-stu-id="513d6-135">SHA-256</span></span>|<span data-ttu-id="513d6-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="513d6-136">0x800c</span></span>|  
|<span data-ttu-id="513d6-137">SHA-384.</span><span class="sxs-lookup"><span data-stu-id="513d6-137">SHA-384</span></span>|<span data-ttu-id="513d6-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="513d6-138">0x800d</span></span>|  
|<span data-ttu-id="513d6-139">SHA-512.</span><span class="sxs-lookup"><span data-stu-id="513d6-139">SHA-512</span></span>|<span data-ttu-id="513d6-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="513d6-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="513d6-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="513d6-141">Requirements</span></span>  
 <span data-ttu-id="513d6-142">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="513d6-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="513d6-143">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="513d6-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="513d6-144">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="513d6-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="513d6-145">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="513d6-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="513d6-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="513d6-146">See Also</span></span>  
 [<span data-ttu-id="513d6-147">StrongNameTokenFromPublicKey (metodo)</span><span class="sxs-lookup"><span data-stu-id="513d6-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="513d6-148">PublicKeyBlob (struttura)</span><span class="sxs-lookup"><span data-stu-id="513d6-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="513d6-149">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="513d6-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="513d6-150">StrongNameGetPublicKey (metodo)</span><span class="sxs-lookup"><span data-stu-id="513d6-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
