---
title: Funzione StrongNameSignatureGenerationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 059dadcaf7a55074e30c59873a8c1e7016b0a33e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666000"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="a6a47-102">Funzione StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="a6a47-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="a6a47-103">Genera una firma con nome sicuro per l'assembly specificato, in base ai flag specificati.</span><span class="sxs-lookup"><span data-stu-id="a6a47-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="a6a47-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="a6a47-104">This function has been deprecated.</span></span> <span data-ttu-id="a6a47-105">Usare la [StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="a6a47-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6a47-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6a47-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6a47-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6a47-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a6a47-108">[in] Il percorso del file che contiene il manifesto dell'assembly per le quali verrà generata la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="a6a47-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="a6a47-109">[in] Il nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="a6a47-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="a6a47-110">Se `pbKeyBlob` è null, `wszKeyContainer` deve specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="a6a47-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="a6a47-111">In questo caso, la coppia di chiavi archiviata nel contenitore viene usata per firmare il file.</span><span class="sxs-lookup"><span data-stu-id="a6a47-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="a6a47-112">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().</span><span class="sxs-lookup"><span data-stu-id="a6a47-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="a6a47-113">[in] Un puntatore per la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="a6a47-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="a6a47-114">Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione).</span><span class="sxs-lookup"><span data-stu-id="a6a47-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="a6a47-115">Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `wszKeyContainer` si presuppone che contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="a6a47-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="a6a47-116">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="a6a47-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="a6a47-117">[out] Puntatore alla posizione in cui common language runtime restituisce la firma.</span><span class="sxs-lookup"><span data-stu-id="a6a47-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="a6a47-118">Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="a6a47-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="a6a47-119">Se `ppbSignatureBlob` è non null, common language runtime alloca spazio in cui si desidera ottenere la firma.</span><span class="sxs-lookup"><span data-stu-id="a6a47-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="a6a47-120">Il chiamante deve liberare questo spazio usando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="a6a47-120">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="a6a47-121">[out] Le dimensioni, in byte, della firma restituita.</span><span class="sxs-lookup"><span data-stu-id="a6a47-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a6a47-122">[in] Uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6a47-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="a6a47-123">`SN_SIGN_ALL_FILES` (0x00000001) - ricalcola tutti gli hash per i moduli collegati.</span><span class="sxs-lookup"><span data-stu-id="a6a47-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="a6a47-124">`SN_TEST_SIGN` (0x00000002) - test la firma dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a6a47-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6a47-125">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a6a47-125">Return Value</span></span>  
 <span data-ttu-id="a6a47-126">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a6a47-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6a47-127">Note</span><span class="sxs-lookup"><span data-stu-id="a6a47-127">Remarks</span></span>  
 <span data-ttu-id="a6a47-128">Specificare null per `wszFilePath` per calcolare le dimensioni della firma senza la creazione della firma.</span><span class="sxs-lookup"><span data-stu-id="a6a47-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="a6a47-129">La firma possa essere archiviata direttamente nel file o restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="a6a47-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="a6a47-130">Se `SN_SIGN_ALL_FILES` è specificato ma non è inclusa una chiave pubblica (entrambe `pbKeyBlob` e `wszFilePath` sono null), vengono ricalcolati gli hash per moduli collegati, ma l'assembly non firmato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="a6a47-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="a6a47-131">Se `SN_TEST_SIGN` viene specificato, l'intestazione common language runtime non viene modificata per indicare che l'assembly è firmato con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="a6a47-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="a6a47-132">Se il `StrongNameSignatureGenerationEx` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="a6a47-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6a47-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6a47-133">Requirements</span></span>  
 <span data-ttu-id="a6a47-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6a47-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6a47-135">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a6a47-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a6a47-136">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a6a47-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6a47-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6a47-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a47-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6a47-138">See also</span></span>

- [<span data-ttu-id="a6a47-139">Metodo StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="a6a47-139">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="a6a47-140">Metodo StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="a6a47-140">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="a6a47-141">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a6a47-141">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
