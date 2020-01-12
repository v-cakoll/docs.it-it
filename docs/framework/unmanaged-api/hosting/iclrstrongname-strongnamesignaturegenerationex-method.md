---
title: Metodo ICLRStrongName::StrongNameSignatureGenerationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
ms.openlocfilehash: 34614fe24127787a113bab4975a50f1c8d2d875e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899503"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="e0906-102">Metodo ICLRStrongName::StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="e0906-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="e0906-103">Genera una firma con nome sicuro per l'assembly specificato, in base ai flag specificati.</span><span class="sxs-lookup"><span data-stu-id="e0906-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0906-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0906-104">Syntax</span></span>  
  
```cpp
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0906-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0906-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="e0906-106">in Percorso del file contenente il manifesto dell'assembly per il quale verrà generata la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e0906-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="e0906-107">in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="e0906-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="e0906-108">Se `pbKeyBlob` è null, `wszKeyContainer` necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="e0906-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="e0906-109">In questo caso, la coppia di chiavi archiviata nel contenitore viene usata per firmare il file.</span><span class="sxs-lookup"><span data-stu-id="e0906-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="e0906-110">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.</span><span class="sxs-lookup"><span data-stu-id="e0906-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="e0906-111">in Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="e0906-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="e0906-112">Questa coppia è nel formato creato dalla funzione Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="e0906-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="e0906-113">Se `pbKeyBlob` è null, si presuppone che il contenitore di chiavi specificato da `wszKeyContainer` contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="e0906-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="e0906-114">in Dimensione, in byte, del `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="e0906-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="e0906-115">out Puntatore alla posizione in cui il Common Language Runtime restituisce la firma.</span><span class="sxs-lookup"><span data-stu-id="e0906-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="e0906-116">Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="e0906-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="e0906-117">Se `ppbSignatureBlob` non è null, il Common Language Runtime alloca spazio per la restituzione della firma.</span><span class="sxs-lookup"><span data-stu-id="e0906-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="e0906-118">Il chiamante deve liberare questo spazio usando il metodo [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e0906-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="e0906-119">out Dimensione, in byte, della firma restituita.</span><span class="sxs-lookup"><span data-stu-id="e0906-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e0906-120">in Uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0906-120">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="e0906-121">`SN_SIGN_ALL_FILES` (0x00000001): Ricalcola tutti gli hash per i moduli collegati.</span><span class="sxs-lookup"><span data-stu-id="e0906-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="e0906-122">`SN_TEST_SIGN` (0x00000002)-testare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="e0906-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0906-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e0906-123">Return Value</span></span>  
 <span data-ttu-id="e0906-124">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="e0906-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0906-125">Note</span><span class="sxs-lookup"><span data-stu-id="e0906-125">Remarks</span></span>  
 <span data-ttu-id="e0906-126">Specificare null per `wszFilePath` per calcolare le dimensioni della firma senza creare la firma.</span><span class="sxs-lookup"><span data-stu-id="e0906-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="e0906-127">La firma può essere archiviata direttamente nel file o restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="e0906-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="e0906-128">Se `SN_SIGN_ALL_FILES` è specificato ma non è inclusa una chiave pubblica (sia `pbKeyBlob` che `wszFilePath` sono null), gli hash per i moduli collegati vengono ricalcolati, ma l'assembly non viene firmato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="e0906-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="e0906-129">Se `SN_TEST_SIGN` viene specificato, l'intestazione Common Language Runtime non viene modificata per indicare che l'assembly è firmato con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e0906-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0906-130">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e0906-130">Requirements</span></span>  
 <span data-ttu-id="e0906-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0906-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0906-132">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="e0906-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e0906-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e0906-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0906-134">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0906-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0906-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0906-135">See also</span></span>

- [<span data-ttu-id="e0906-136">Metodo StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="e0906-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="e0906-137">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e0906-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
