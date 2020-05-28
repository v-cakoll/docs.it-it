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
ms.openlocfilehash: 1904a98f254a988ce035847a4cdeede182aa07bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006376"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="acffa-102">Metodo StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="acffa-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="acffa-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="acffa-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acffa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="acffa-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="acffa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="acffa-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="acffa-106">in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="acffa-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="acffa-107">Se `pbKeyBlob` è null, è `szKeyContainer` necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="acffa-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="acffa-108">In questo caso, il `StrongNameGetPublicKeyEx` metodo estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="acffa-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="acffa-109">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.</span><span class="sxs-lookup"><span data-stu-id="acffa-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="acffa-110">Le chiavi devono essere chiavi di firma Rivest-Shamir-Adleman (RSA) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="acffa-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="acffa-111">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="acffa-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="acffa-112">in Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="acffa-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="acffa-113">Questa coppia è nel formato creato dalla `CryptExportKey` funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="acffa-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="acffa-114">Se `pbKeyBlob` è null, si presuppone che il contenitore di chiavi specificato da `szKeyContainer` contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="acffa-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="acffa-115">in Dimensione, in byte, di `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="acffa-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="acffa-116">out BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="acffa-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="acffa-117">Il `ppbPublicKeyBlob` parametro viene allocato dal Common Language Runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="acffa-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="acffa-118">Il chiamante deve liberare la memoria tramite il metodo [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="acffa-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="acffa-119">out Dimensioni del BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="acffa-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="acffa-120">in Algoritmo hash dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="acffa-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="acffa-121">Per un elenco dei valori accettati, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="acffa-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="acffa-122">in Riservato per un utilizzo futuro; il valore predefinito è null.</span><span class="sxs-lookup"><span data-stu-id="acffa-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acffa-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="acffa-123">Return Value</span></span>  
 <span data-ttu-id="acffa-124">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="acffa-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acffa-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="acffa-125">Remarks</span></span>  
 <span data-ttu-id="acffa-126">La chiave pubblica è contenuta in una struttura [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="acffa-126">The public key is contained in a [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acffa-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="acffa-127">Remarks</span></span>  
 <span data-ttu-id="acffa-128">Nella tabella seguente viene illustrato il set di valori accettati per il `uHashAlgId` parametro.</span><span class="sxs-lookup"><span data-stu-id="acffa-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="acffa-129">Nome</span><span class="sxs-lookup"><span data-stu-id="acffa-129">Name</span></span>|<span data-ttu-id="acffa-130">valore</span><span class="sxs-lookup"><span data-stu-id="acffa-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="acffa-131">Nessuno</span><span class="sxs-lookup"><span data-stu-id="acffa-131">None</span></span>|<span data-ttu-id="acffa-132">0</span><span class="sxs-lookup"><span data-stu-id="acffa-132">0</span></span>|  
|<span data-ttu-id="acffa-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="acffa-133">SHA-1</span></span>|<span data-ttu-id="acffa-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="acffa-134">0x8004</span></span>|  
|<span data-ttu-id="acffa-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="acffa-135">SHA-256</span></span>|<span data-ttu-id="acffa-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="acffa-136">0x800c</span></span>|  
|<span data-ttu-id="acffa-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="acffa-137">SHA-384</span></span>|<span data-ttu-id="acffa-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="acffa-138">0x800d</span></span>|  
|<span data-ttu-id="acffa-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="acffa-139">SHA-512</span></span>|<span data-ttu-id="acffa-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="acffa-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acffa-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="acffa-141">Requirements</span></span>  
 <span data-ttu-id="acffa-142">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acffa-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acffa-143">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="acffa-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="acffa-144">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="acffa-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acffa-145">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acffa-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acffa-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acffa-146">See also</span></span>

- [<span data-ttu-id="acffa-147">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="acffa-147">StrongNameTokenFromPublicKey Method</span></span>](iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="acffa-148">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="acffa-148">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="acffa-149">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="acffa-149">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
- [<span data-ttu-id="acffa-150">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="acffa-150">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
