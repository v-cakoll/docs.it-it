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
ms.openlocfilehash: 700bcc5b818c452d3642d325fb6fe19cbb162474
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141453"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="f9708-102">Metodo StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="f9708-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="f9708-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="f9708-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9708-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9708-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f9708-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9708-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="f9708-106">in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="f9708-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="f9708-107">Se `pbKeyBlob` è null, `szKeyContainer` necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="f9708-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="f9708-108">In questo caso, il metodo `StrongNameGetPublicKeyEx` estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="f9708-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="f9708-109">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.</span><span class="sxs-lookup"><span data-stu-id="f9708-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="f9708-110">Le chiavi devono essere chiavi di firma Rivest-Shamir-Adleman (RSA) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="f9708-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="f9708-111">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="f9708-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="f9708-112">in Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="f9708-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="f9708-113">Questa coppia è nel formato creato dalla funzione Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="f9708-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="f9708-114">Se `pbKeyBlob` è null, si presuppone che il contenitore di chiavi specificato da `szKeyContainer` contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="f9708-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="f9708-115">in Dimensione, in byte, del `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="f9708-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="f9708-116">out BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="f9708-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="f9708-117">Il parametro `ppbPublicKeyBlob` viene allocato dall'Common Language Runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="f9708-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="f9708-118">Il chiamante deve liberare la memoria tramite il metodo [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f9708-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="f9708-119">out Dimensioni del BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="f9708-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="f9708-120">in Algoritmo hash dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f9708-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="f9708-121">Per un elenco dei valori accettati, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="f9708-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="f9708-122">in Riservato per un utilizzo futuro; il valore predefinito è null.</span><span class="sxs-lookup"><span data-stu-id="f9708-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9708-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f9708-123">Return Value</span></span>  
 <span data-ttu-id="f9708-124">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="f9708-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9708-125">Note</span><span class="sxs-lookup"><span data-stu-id="f9708-125">Remarks</span></span>  
 <span data-ttu-id="f9708-126">La chiave pubblica è contenuta in una struttura [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="f9708-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9708-127">Note</span><span class="sxs-lookup"><span data-stu-id="f9708-127">Remarks</span></span>  
 <span data-ttu-id="f9708-128">Nella tabella seguente viene illustrato il set di valori accettati per il parametro `uHashAlgId`.</span><span class="sxs-lookup"><span data-stu-id="f9708-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="f9708-129">Name</span><span class="sxs-lookup"><span data-stu-id="f9708-129">Name</span></span>|<span data-ttu-id="f9708-130">Value</span><span class="sxs-lookup"><span data-stu-id="f9708-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="f9708-131">Nessuno</span><span class="sxs-lookup"><span data-stu-id="f9708-131">None</span></span>|<span data-ttu-id="f9708-132">0</span><span class="sxs-lookup"><span data-stu-id="f9708-132">0</span></span>|  
|<span data-ttu-id="f9708-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="f9708-133">SHA-1</span></span>|<span data-ttu-id="f9708-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="f9708-134">0x8004</span></span>|  
|<span data-ttu-id="f9708-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="f9708-135">SHA-256</span></span>|<span data-ttu-id="f9708-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="f9708-136">0x800c</span></span>|  
|<span data-ttu-id="f9708-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="f9708-137">SHA-384</span></span>|<span data-ttu-id="f9708-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="f9708-138">0x800d</span></span>|  
|<span data-ttu-id="f9708-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="f9708-139">SHA-512</span></span>|<span data-ttu-id="f9708-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="f9708-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9708-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9708-141">Requirements</span></span>  
 <span data-ttu-id="f9708-142">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9708-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9708-143">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f9708-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f9708-144">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f9708-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9708-145">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9708-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9708-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9708-146">See also</span></span>

- [<span data-ttu-id="f9708-147">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="f9708-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="f9708-148">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="f9708-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="f9708-149">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f9708-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="f9708-150">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="f9708-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
