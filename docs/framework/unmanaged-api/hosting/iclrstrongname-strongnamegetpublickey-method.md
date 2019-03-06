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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e66835ec1cdf1327a39223b6cdb187ec47cd7e3d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476308"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="c8fd6-102">Metodo ICLRStrongName::StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="c8fd6-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="c8fd6-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="c8fd6-104">La coppia di chiavi può essere fornita come un nome di contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come una raccolta di byte non elaborata.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8fd6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8fd6-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8fd6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8fd6-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="c8fd6-107">[in] Il nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="c8fd6-108">Se `pbKeyBlob` è null, `szKeyContainer` deve specificare un contenitore valido all'interno del CSP.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="c8fd6-109">In questo caso, il [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) metodo estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="c8fd6-110">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().</span><span class="sxs-lookup"><span data-stu-id="c8fd6-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="c8fd6-111">Le chiavi devono essere Rivest-Shamir-Adleman (RSA di 1024 bit) le chiavi di firma.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="c8fd6-112">Nessun altro tipo di chiavi è supportato in questo momento.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="c8fd6-113">[in] Un puntatore per la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="c8fd6-114">Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione).</span><span class="sxs-lookup"><span data-stu-id="c8fd6-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="c8fd6-115">Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `szKeyContainer` si presuppone che contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="c8fd6-116">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="c8fd6-117">[out] Chiave pubblica restituita BLOB.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="c8fd6-118">Il `ppbPublicKeyBlob` parametro è allocata da common language runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="c8fd6-119">Il chiamante deve liberare la memoria usando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c8fd6-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="c8fd6-120">[out] Le dimensioni della chiave pubblica BLOB restituita.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8fd6-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c8fd6-121">Return Value</span></span>  
 <span data-ttu-id="c8fd6-122">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="c8fd6-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8fd6-123">Note</span><span class="sxs-lookup"><span data-stu-id="c8fd6-123">Remarks</span></span>  
 <span data-ttu-id="c8fd6-124">La chiave pubblica è contenuta un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="c8fd6-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8fd6-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8fd6-125">Requirements</span></span>  
 <span data-ttu-id="c8fd6-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8fd6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8fd6-127">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c8fd6-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c8fd6-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c8fd6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8fd6-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8fd6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8fd6-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8fd6-130">See also</span></span>
- [<span data-ttu-id="c8fd6-131">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="c8fd6-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="c8fd6-132">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="c8fd6-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="c8fd6-133">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c8fd6-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
