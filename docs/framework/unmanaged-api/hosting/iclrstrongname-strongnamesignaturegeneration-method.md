---
title: Metodo ICLRStrongName::StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 679afd7b1053043a7cc43304a544a516024a4696
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165782"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="8f6a1-102">Metodo ICLRStrongName::StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="8f6a1-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="8f6a1-103">Genera una firma con nome sicuro per l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f6a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f6a1-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f6a1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f6a1-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8f6a1-106">[in] Il percorso del file che contiene il manifesto dell'assembly per le quali verrà generata la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="8f6a1-107">[in] Il nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="8f6a1-108">Se `pbKeyBlob` è null, `wszKeyContainer` deve specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="8f6a1-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="8f6a1-109">In questo caso, la coppia di chiavi archiviata nel contenitore viene usata per firmare il file.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="8f6a1-110">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().</span><span class="sxs-lookup"><span data-stu-id="8f6a1-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="8f6a1-111">Le chiavi devono essere Rivest-Shamir-Adleman (RSA di 1024 bit) le chiavi di firma.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="8f6a1-112">Nessun altro tipo di chiavi è supportato in questo momento.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="8f6a1-113">[in] Un puntatore per la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="8f6a1-114">Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione).</span><span class="sxs-lookup"><span data-stu-id="8f6a1-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="8f6a1-115">Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `wszKeyContainer` si presuppone che contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="8f6a1-116">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="8f6a1-117">[out] Puntatore alla posizione in cui common language runtime restituisce la firma.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="8f6a1-118">Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="8f6a1-119">Se `ppbSignatureBlob` è non null, common language runtime alloca spazio in cui si desidera ottenere la firma.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="8f6a1-120">Il chiamante deve liberare questo spazio tramite il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="8f6a1-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="8f6a1-121">[out] Le dimensioni, in byte, della firma restituita.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f6a1-122">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8f6a1-122">Return Value</span></span>  
 <span data-ttu-id="8f6a1-123">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="8f6a1-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f6a1-124">Note</span><span class="sxs-lookup"><span data-stu-id="8f6a1-124">Remarks</span></span>  
 <span data-ttu-id="8f6a1-125">Specificare null per `wszFilePath` per calcolare le dimensioni della firma senza la creazione della firma.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="8f6a1-126">La firma possa essere archiviati utilizzando direttamente il file o restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="8f6a1-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f6a1-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f6a1-127">Requirements</span></span>  
 <span data-ttu-id="8f6a1-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f6a1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f6a1-129">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8f6a1-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8f6a1-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8f6a1-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f6a1-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f6a1-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6a1-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f6a1-132">See also</span></span>

- [<span data-ttu-id="8f6a1-133">Metodo StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="8f6a1-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="8f6a1-134">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8f6a1-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
