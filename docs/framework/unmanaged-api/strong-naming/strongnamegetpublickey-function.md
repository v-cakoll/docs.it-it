---
title: Funzione StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e38a85b688d66e9f44bd8026bb4c9e141a6eb7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229290"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="3700c-102">Funzione StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="3700c-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="3700c-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="3700c-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="3700c-104">La coppia di chiavi può essere fornita come un nome di contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come una raccolta di byte non elaborata.</span><span class="sxs-lookup"><span data-stu-id="3700c-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="3700c-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="3700c-105">This function has been deprecated.</span></span> <span data-ttu-id="3700c-106">Usare la [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="3700c-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3700c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3700c-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3700c-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="3700c-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="3700c-109">[in] Il nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="3700c-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="3700c-110">Se `pbKeyBlob` è null, `szKeyContainer` deve specificare un contenitore valido all'interno del CSP.</span><span class="sxs-lookup"><span data-stu-id="3700c-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="3700c-111">In questo caso, `StrongNameGetPublicKey` estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="3700c-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="3700c-112">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().</span><span class="sxs-lookup"><span data-stu-id="3700c-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="3700c-113">Le chiavi devono essere Rivest-Shamir-Adleman (RSA di 1024 bit) le chiavi di firma.</span><span class="sxs-lookup"><span data-stu-id="3700c-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="3700c-114">Nessun altro tipo di chiavi è supportato in questo momento.</span><span class="sxs-lookup"><span data-stu-id="3700c-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="3700c-115">[in] Un puntatore per la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="3700c-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="3700c-116">Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione).</span><span class="sxs-lookup"><span data-stu-id="3700c-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="3700c-117">Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `szKeyContainer` si presuppone che contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="3700c-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="3700c-118">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="3700c-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="3700c-119">[out] Chiave pubblica restituita BLOB.</span><span class="sxs-lookup"><span data-stu-id="3700c-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="3700c-120">Il `ppbPublicKeyBlob` parametro è allocata da common language runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="3700c-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="3700c-121">Il chiamante deve liberare la memoria usando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="3700c-121">The caller must free the memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="3700c-122">[out] Le dimensioni della chiave pubblica BLOB restituita.</span><span class="sxs-lookup"><span data-stu-id="3700c-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3700c-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3700c-123">Return Value</span></span>  
 <span data-ttu-id="3700c-124">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3700c-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3700c-125">Note</span><span class="sxs-lookup"><span data-stu-id="3700c-125">Remarks</span></span>  
 <span data-ttu-id="3700c-126">La chiave pubblica è contenuta un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="3700c-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="3700c-127">Se il `StrongNameGetPublicKey` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="3700c-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3700c-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3700c-128">Requirements</span></span>  
 <span data-ttu-id="3700c-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3700c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3700c-130">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="3700c-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3700c-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3700c-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3700c-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3700c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3700c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3700c-133">See also</span></span>

- [<span data-ttu-id="3700c-134">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="3700c-134">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="3700c-135">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="3700c-135">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="3700c-136">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3700c-136">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="3700c-137">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="3700c-137">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
