---
title: Metodo ICLRStrongName::StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
ms.openlocfilehash: 943251357a91ea9ae3d492fa7bf20eebf948b8b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135069"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="bae79-102">Metodo ICLRStrongName::StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="bae79-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="bae79-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="bae79-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="bae79-104">È possibile specificare la coppia di chiavi come nome del contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come raccolta di byte non elaborata.</span><span class="sxs-lookup"><span data-stu-id="bae79-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bae79-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bae79-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bae79-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="bae79-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="bae79-107">in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="bae79-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="bae79-108">Se `pbKeyBlob` è null, `szKeyContainer` necessario specificare un contenitore valido all'interno del CSP.</span><span class="sxs-lookup"><span data-stu-id="bae79-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="bae79-109">In questo caso, il metodo [ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="bae79-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="bae79-110">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.</span><span class="sxs-lookup"><span data-stu-id="bae79-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="bae79-111">Le chiavi devono essere chiavi di firma Rivest-Shamir-Adleman (RSA) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="bae79-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="bae79-112">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="bae79-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="bae79-113">in Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="bae79-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="bae79-114">Questa coppia è nel formato creato dalla funzione Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="bae79-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="bae79-115">Se `pbKeyBlob` è null, si presuppone che il contenitore di chiavi specificato da `szKeyContainer` contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="bae79-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="bae79-116">in Dimensione, in byte, del `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="bae79-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="bae79-117">out BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="bae79-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="bae79-118">Il parametro `ppbPublicKeyBlob` viene allocato dall'Common Language Runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="bae79-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="bae79-119">Il chiamante deve liberare la memoria tramite il metodo [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bae79-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="bae79-120">out Dimensioni del BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="bae79-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bae79-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bae79-121">Return Value</span></span>  
 <span data-ttu-id="bae79-122">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="bae79-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bae79-123">Note</span><span class="sxs-lookup"><span data-stu-id="bae79-123">Remarks</span></span>  
 <span data-ttu-id="bae79-124">La chiave pubblica è contenuta in una struttura [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="bae79-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bae79-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bae79-125">Requirements</span></span>  
 <span data-ttu-id="bae79-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bae79-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bae79-127">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="bae79-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bae79-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bae79-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bae79-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bae79-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae79-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bae79-130">See also</span></span>

- [<span data-ttu-id="bae79-131">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="bae79-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="bae79-132">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="bae79-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="bae79-133">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="bae79-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
