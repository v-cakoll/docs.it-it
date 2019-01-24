---
title: Funzione StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a33c2240a0e3f3a09ff5ce93c34db9bba03ab83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665071"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="ea4bd-102">Funzione StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="ea4bd-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="ea4bd-103">Genera una firma con nome sicuro per l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="ea4bd-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-104">This function has been deprecated.</span></span> <span data-ttu-id="ea4bd-105">Usare la [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea4bd-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea4bd-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea4bd-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea4bd-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ea4bd-108">[in] Il percorso del file che contiene il manifesto dell'assembly per le quali verrà generata la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="ea4bd-109">[in] Il nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="ea4bd-110">Se `pbKeyBlob` è null, `wszKeyContainer` deve specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="ea4bd-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="ea4bd-111">In questo caso, la coppia di chiavi archiviata nel contenitore viene usata per firmare il file.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="ea4bd-112">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().</span><span class="sxs-lookup"><span data-stu-id="ea4bd-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="ea4bd-113">Le chiavi devono essere Rivest-Shamir-Adleman (RSA di 1024 bit) le chiavi di firma.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="ea4bd-114">Nessun altro tipo di chiavi è supportato in questo momento.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="ea4bd-115">[in] Un puntatore per la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="ea4bd-116">Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione).</span><span class="sxs-lookup"><span data-stu-id="ea4bd-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="ea4bd-117">Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `wszKeyContainer` si presuppone che contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="ea4bd-118">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="ea4bd-119">[out] Puntatore alla posizione in cui common language runtime restituisce la firma.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="ea4bd-120">Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="ea4bd-121">Se `ppbSignatureBlob` è non null, common language runtime alloca spazio in cui si desidera ottenere la firma.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="ea4bd-122">Il chiamante deve liberare questo spazio usando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="ea4bd-122">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="ea4bd-123">[out] Le dimensioni, in byte, della firma restituita.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea4bd-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ea4bd-124">Return Value</span></span>  
 <span data-ttu-id="ea4bd-125">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea4bd-126">Note</span><span class="sxs-lookup"><span data-stu-id="ea4bd-126">Remarks</span></span>  
 <span data-ttu-id="ea4bd-127">Specificare null per `wszFilePath` per calcolare le dimensioni della firma senza la creazione della firma.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="ea4bd-128">La firma possa essere archiviati utilizzando direttamente il file o restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="ea4bd-129">Se il `StrongNameSignatureGeneration` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="ea4bd-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea4bd-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea4bd-130">Requirements</span></span>  
 <span data-ttu-id="ea4bd-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea4bd-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea4bd-132">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ea4bd-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ea4bd-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ea4bd-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea4bd-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea4bd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea4bd-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea4bd-135">See also</span></span>
- [<span data-ttu-id="ea4bd-136">Metodo StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="ea4bd-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="ea4bd-137">Metodo StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="ea4bd-137">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="ea4bd-138">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ea4bd-138">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
