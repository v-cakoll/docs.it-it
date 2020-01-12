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
ms.openlocfilehash: ced7540afe931fb91240c770d76d205400157a51
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901095"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="115da-102">Metodo ICLRStrongName::StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="115da-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="115da-103">Genera una firma con nome sicuro per l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="115da-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="115da-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="115da-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="115da-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="115da-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="115da-106">in Percorso del file contenente il manifesto dell'assembly per il quale verrà generata la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="115da-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="115da-107">in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="115da-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="115da-108">Se `pbKeyBlob` è null, `wszKeyContainer` necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="115da-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="115da-109">In questo caso, la coppia di chiavi archiviata nel contenitore viene usata per firmare il file.</span><span class="sxs-lookup"><span data-stu-id="115da-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="115da-110">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.</span><span class="sxs-lookup"><span data-stu-id="115da-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="115da-111">Le chiavi devono essere chiavi di firma Rivest-Shamir-Adleman (RSA) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="115da-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="115da-112">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="115da-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="115da-113">in Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="115da-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="115da-114">Questa coppia è nel formato creato dalla funzione Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="115da-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="115da-115">Se `pbKeyBlob` è null, si presuppone che il contenitore di chiavi specificato da `wszKeyContainer` contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="115da-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="115da-116">in Dimensione, in byte, del `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="115da-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="115da-117">out Puntatore alla posizione in cui il Common Language Runtime restituisce la firma.</span><span class="sxs-lookup"><span data-stu-id="115da-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="115da-118">Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="115da-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="115da-119">Se `ppbSignatureBlob` non è null, il Common Language Runtime alloca spazio per la restituzione della firma.</span><span class="sxs-lookup"><span data-stu-id="115da-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="115da-120">Il chiamante deve liberare questo spazio usando il metodo [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="115da-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="115da-121">out Dimensione, in byte, della firma restituita.</span><span class="sxs-lookup"><span data-stu-id="115da-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="115da-122">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="115da-122">Return Value</span></span>  
 <span data-ttu-id="115da-123">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="115da-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="115da-124">Note</span><span class="sxs-lookup"><span data-stu-id="115da-124">Remarks</span></span>  
 <span data-ttu-id="115da-125">Specificare null per `wszFilePath` per calcolare le dimensioni della firma senza creare la firma.</span><span class="sxs-lookup"><span data-stu-id="115da-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="115da-126">La firma può essere archiviata direttamente nel file o restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="115da-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="115da-127">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="115da-127">Requirements</span></span>  
 <span data-ttu-id="115da-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="115da-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="115da-129">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="115da-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="115da-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="115da-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="115da-131">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="115da-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="115da-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="115da-132">See also</span></span>

- [<span data-ttu-id="115da-133">Metodo StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="115da-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="115da-134">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="115da-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
