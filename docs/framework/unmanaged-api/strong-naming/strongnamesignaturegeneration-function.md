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
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176903"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="58324-102">Funzione StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="58324-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="58324-103">Genera una firma con nome sicuro per l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="58324-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="58324-104">Questa funzione è deprecata.</span><span class="sxs-lookup"><span data-stu-id="58324-104">This function has been deprecated.</span></span> <span data-ttu-id="58324-105">Utilizzare invece il metodo [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) .</span><span class="sxs-lookup"><span data-stu-id="58324-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58324-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58324-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58324-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="58324-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="58324-108">[in] Percorso del file che contiene il manifesto dell'assembly per il quale verrà generata la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="58324-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="58324-109">[in] Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="58324-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="58324-110">Se `pbKeyBlob` è `wszKeyContainer` null, è necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="58324-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="58324-111">In questo caso, la coppia di chiavi archiviata nel contenitore viene utilizzata per firmare il file.</span><span class="sxs-lookup"><span data-stu-id="58324-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="58324-112">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nell'oggetto binario di grandi dimensioni chiave (BLOB).</span><span class="sxs-lookup"><span data-stu-id="58324-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="58324-113">Le chiavi devono essere chiavi di firma RSA (Rivest-Shamir-Adleman) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="58324-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="58324-114">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="58324-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="58324-115">[in] Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="58324-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="58324-116">Questa coppia è nel formato creato `CryptExportKey` dalla funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="58324-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="58324-117">Se `pbKeyBlob` è null, si `wszKeyContainer` presuppone che il contenitore di chiavi specificato da contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="58324-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="58324-118">[in] Dimensione, in byte, `pbKeyBlob`di .</span><span class="sxs-lookup"><span data-stu-id="58324-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="58324-119">[fuori] Puntatore al percorso in cui Common Language Runtime restituisce la firma.</span><span class="sxs-lookup"><span data-stu-id="58324-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="58324-120">Se `ppbSignatureBlob` è null, il runtime archivia `wszFilePath`la firma nel file specificato da .</span><span class="sxs-lookup"><span data-stu-id="58324-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="58324-121">Se `ppbSignatureBlob` non è null, Common Language Runtime alloca lo spazio in cui restituire la firma.</span><span class="sxs-lookup"><span data-stu-id="58324-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="58324-122">Il chiamante deve liberare questo spazio utilizzando la funzione [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)</span><span class="sxs-lookup"><span data-stu-id="58324-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="58324-123">[fuori] Dimensione, in byte, della firma restituita.</span><span class="sxs-lookup"><span data-stu-id="58324-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58324-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="58324-124">Return Value</span></span>  
 <span data-ttu-id="58324-125">`true`al termine del successo; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="58324-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58324-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="58324-126">Remarks</span></span>  
 <span data-ttu-id="58324-127">Specificare `wszFilePath` null per calcolare la dimensione della firma senza creare la firma.</span><span class="sxs-lookup"><span data-stu-id="58324-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="58324-128">La firma può essere archiviata direttamente nel file o restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="58324-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="58324-129">Se `StrongNameSignatureGeneration` la funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="58324-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58324-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58324-130">Requirements</span></span>  
 <span data-ttu-id="58324-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58324-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58324-132">**Intestazione:** NomeForte.h</span><span class="sxs-lookup"><span data-stu-id="58324-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="58324-133">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58324-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58324-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58324-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58324-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58324-135">See also</span></span>

- [<span data-ttu-id="58324-136">Metodo StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="58324-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="58324-137">Metodo StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="58324-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="58324-138">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="58324-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
