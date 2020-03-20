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
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176227"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="745e9-102">Metodo StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="745e9-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="745e9-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="745e9-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="745e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="745e9-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="745e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="745e9-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="745e9-106">[in] Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="745e9-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="745e9-107">Se `pbKeyBlob` è `szKeyContainer` null, è necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="745e9-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="745e9-108">In questo caso, il `StrongNameGetPublicKeyEx` metodo estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="745e9-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="745e9-109">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nell'oggetto binario di grandi dimensioni chiave (BLOB).</span><span class="sxs-lookup"><span data-stu-id="745e9-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="745e9-110">Le chiavi devono essere chiavi di firma RSA (Rivest-Shamir-Adleman) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="745e9-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="745e9-111">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="745e9-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="745e9-112">[in] Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="745e9-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="745e9-113">Questa coppia è nel formato creato `CryptExportKey` dalla funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="745e9-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="745e9-114">Se `pbKeyBlob` è null, si `szKeyContainer` presuppone che il contenitore di chiavi specificato da contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="745e9-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="745e9-115">[in] Dimensione, in byte, `pbKeyBlob`di .</span><span class="sxs-lookup"><span data-stu-id="745e9-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="745e9-116">[fuori] BLOB della chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="745e9-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="745e9-117">Il `ppbPublicKeyBlob` parametro viene allocato da Common Language Runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="745e9-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="745e9-118">Il chiamante deve liberare la memoria utilizzando il metodo [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="745e9-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="745e9-119">[fuori] Dimensione del BLOB della chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="745e9-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="745e9-120">[in] Algoritmo hash dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="745e9-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="745e9-121">Vedere la sezione Osservazioni per un elenco dei valori accettati.</span><span class="sxs-lookup"><span data-stu-id="745e9-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="745e9-122">[in] Riservato per uso futuro; il valore predefinito è null.</span><span class="sxs-lookup"><span data-stu-id="745e9-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="745e9-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="745e9-123">Return Value</span></span>  
 <span data-ttu-id="745e9-124">`S_OK`se il metodo è stato completato correttamente; in caso contrario, un valore HRESULT che indica un errore (vedere [Valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="745e9-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="745e9-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="745e9-125">Remarks</span></span>  
 <span data-ttu-id="745e9-126">La chiave pubblica è contenuta in una struttura [PublicKeyBlob.The public](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) key is contained in a PublicKeyBlob structure.</span><span class="sxs-lookup"><span data-stu-id="745e9-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="745e9-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="745e9-127">Remarks</span></span>  
 <span data-ttu-id="745e9-128">Nella tabella seguente viene illustrato il `uHashAlgId` set di valori accettati per il parametro.</span><span class="sxs-lookup"><span data-stu-id="745e9-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="745e9-129">Nome</span><span class="sxs-lookup"><span data-stu-id="745e9-129">Name</span></span>|<span data-ttu-id="745e9-130">valore</span><span class="sxs-lookup"><span data-stu-id="745e9-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="745e9-131">nessuno</span><span class="sxs-lookup"><span data-stu-id="745e9-131">None</span></span>|<span data-ttu-id="745e9-132">0</span><span class="sxs-lookup"><span data-stu-id="745e9-132">0</span></span>|  
|<span data-ttu-id="745e9-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="745e9-133">SHA-1</span></span>|<span data-ttu-id="745e9-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="745e9-134">0x8004</span></span>|  
|<span data-ttu-id="745e9-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="745e9-135">SHA-256</span></span>|<span data-ttu-id="745e9-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="745e9-136">0x800c</span></span>|  
|<span data-ttu-id="745e9-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="745e9-137">SHA-384</span></span>|<span data-ttu-id="745e9-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="745e9-138">0x800d</span></span>|  
|<span data-ttu-id="745e9-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="745e9-139">SHA-512</span></span>|<span data-ttu-id="745e9-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="745e9-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="745e9-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="745e9-141">Requirements</span></span>  
 <span data-ttu-id="745e9-142">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="745e9-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="745e9-143">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="745e9-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="745e9-144">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="745e9-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="745e9-145">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="745e9-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="745e9-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="745e9-146">See also</span></span>

- [<span data-ttu-id="745e9-147">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="745e9-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="745e9-148">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="745e9-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="745e9-149">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="745e9-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="745e9-150">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="745e9-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
