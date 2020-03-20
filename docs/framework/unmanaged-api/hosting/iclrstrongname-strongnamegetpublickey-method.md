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
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181929"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="a83a7-102">Metodo ICLRStrongName::StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="a83a7-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="a83a7-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="a83a7-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="a83a7-104">La coppia di chiavi può essere fornita come nome del contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come raccolta non elaborata di byte.</span><span class="sxs-lookup"><span data-stu-id="a83a7-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a83a7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a83a7-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a83a7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a83a7-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="a83a7-107">[in] Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="a83a7-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="a83a7-108">Se `pbKeyBlob` è `szKeyContainer` null, è necessario specificare un contenitore valido all'interno del CSP.</span><span class="sxs-lookup"><span data-stu-id="a83a7-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="a83a7-109">In questo caso, il metodo [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="a83a7-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="a83a7-110">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nell'oggetto binario di grandi dimensioni chiave (BLOB).</span><span class="sxs-lookup"><span data-stu-id="a83a7-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="a83a7-111">Le chiavi devono essere chiavi di firma RSA (Rivest-Shamir-Adleman) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="a83a7-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="a83a7-112">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="a83a7-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="a83a7-113">[in] Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="a83a7-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="a83a7-114">Questa coppia è nel formato creato `CryptExportKey` dalla funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="a83a7-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="a83a7-115">Se `pbKeyBlob` è null, si `szKeyContainer` presuppone che il contenitore di chiavi specificato da contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="a83a7-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="a83a7-116">[in] Dimensione, in byte, `pbKeyBlob`di .</span><span class="sxs-lookup"><span data-stu-id="a83a7-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="a83a7-117">[fuori] BLOB della chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="a83a7-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="a83a7-118">Il `ppbPublicKeyBlob` parametro viene allocato da Common Language Runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="a83a7-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="a83a7-119">Il chiamante deve liberare la memoria utilizzando il metodo [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a83a7-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="a83a7-120">[fuori] Dimensione del BLOB della chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="a83a7-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a83a7-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a83a7-121">Return Value</span></span>  
 <span data-ttu-id="a83a7-122">`S_OK`se il metodo è stato completato correttamente; in caso contrario, un valore HRESULT che indica un errore (vedere [Valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="a83a7-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a83a7-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a83a7-123">Remarks</span></span>  
 <span data-ttu-id="a83a7-124">La chiave pubblica è contenuta in una struttura [PublicKeyBlob.The public](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) key is contained in a PublicKeyBlob structure.</span><span class="sxs-lookup"><span data-stu-id="a83a7-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a83a7-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a83a7-125">Requirements</span></span>  
 <span data-ttu-id="a83a7-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a83a7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a83a7-127">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a83a7-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a83a7-128">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a83a7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a83a7-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a83a7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83a7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a83a7-130">See also</span></span>

- [<span data-ttu-id="a83a7-131">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="a83a7-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="a83a7-132">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="a83a7-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="a83a7-133">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a83a7-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
