---
title: Metodo StrongNameGetPublicKeyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b6640e42328fdf840fb0f6d0672b1fdc2c0bc12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694503"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="f731e-102">Metodo StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="f731e-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="f731e-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="f731e-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f731e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f731e-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f731e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f731e-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="f731e-106">[in] Il nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="f731e-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="f731e-107">Se `pbKeyBlob` è null, `szKeyContainer` deve specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="f731e-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="f731e-108">In questo caso, il `StrongNameGetPublicKeyEx` metodo estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="f731e-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="f731e-109">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().</span><span class="sxs-lookup"><span data-stu-id="f731e-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="f731e-110">Le chiavi devono essere Rivest-Shamir-Adleman (RSA di 1024 bit) le chiavi di firma.</span><span class="sxs-lookup"><span data-stu-id="f731e-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="f731e-111">Nessun altro tipo di chiavi è supportato in questo momento.</span><span class="sxs-lookup"><span data-stu-id="f731e-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="f731e-112">[in] Un puntatore per la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="f731e-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="f731e-113">Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione).</span><span class="sxs-lookup"><span data-stu-id="f731e-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="f731e-114">Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `szKeyContainer` si presuppone che contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="f731e-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="f731e-115">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="f731e-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="f731e-116">[out] Chiave pubblica restituita BLOB.</span><span class="sxs-lookup"><span data-stu-id="f731e-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="f731e-117">Il `ppbPublicKeyBlob` parametro è allocata da common language runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="f731e-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="f731e-118">Il chiamante deve liberare la memoria usando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="f731e-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="f731e-119">[out] Le dimensioni della chiave pubblica BLOB restituita.</span><span class="sxs-lookup"><span data-stu-id="f731e-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="f731e-120">[in] L'algoritmo di hash di assembly.</span><span class="sxs-lookup"><span data-stu-id="f731e-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="f731e-121">Vedere la sezione Osservazioni per un elenco di valori accettati.</span><span class="sxs-lookup"><span data-stu-id="f731e-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="f731e-122">[in] Riservato per utilizzi futuri; il valore predefinito è null.</span><span class="sxs-lookup"><span data-stu-id="f731e-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f731e-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f731e-123">Return Value</span></span>  
 <span data-ttu-id="f731e-124">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="f731e-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f731e-125">Note</span><span class="sxs-lookup"><span data-stu-id="f731e-125">Remarks</span></span>  
 <span data-ttu-id="f731e-126">La chiave pubblica è contenuta un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="f731e-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f731e-127">Note</span><span class="sxs-lookup"><span data-stu-id="f731e-127">Remarks</span></span>  
 <span data-ttu-id="f731e-128">Nella tabella seguente mostra il set di valori accettati per il `uHashAlgId` parametro.</span><span class="sxs-lookup"><span data-stu-id="f731e-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="f731e-129">nome</span><span class="sxs-lookup"><span data-stu-id="f731e-129">Name</span></span>|<span data-ttu-id="f731e-130">Valore</span><span class="sxs-lookup"><span data-stu-id="f731e-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="f731e-131">nessuno</span><span class="sxs-lookup"><span data-stu-id="f731e-131">None</span></span>|<span data-ttu-id="f731e-132">0</span><span class="sxs-lookup"><span data-stu-id="f731e-132">0</span></span>|  
|<span data-ttu-id="f731e-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="f731e-133">SHA-1</span></span>|<span data-ttu-id="f731e-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="f731e-134">0x8004</span></span>|  
|<span data-ttu-id="f731e-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="f731e-135">SHA-256</span></span>|<span data-ttu-id="f731e-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="f731e-136">0x800c</span></span>|  
|<span data-ttu-id="f731e-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="f731e-137">SHA-384</span></span>|<span data-ttu-id="f731e-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="f731e-138">0x800d</span></span>|  
|<span data-ttu-id="f731e-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="f731e-139">SHA-512</span></span>|<span data-ttu-id="f731e-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="f731e-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f731e-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f731e-141">Requirements</span></span>  
 <span data-ttu-id="f731e-142">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f731e-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f731e-143">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f731e-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f731e-144">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f731e-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f731e-145">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f731e-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f731e-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f731e-146">See also</span></span>
- [<span data-ttu-id="f731e-147">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="f731e-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="f731e-148">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="f731e-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="f731e-149">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f731e-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="f731e-150">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="f731e-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
