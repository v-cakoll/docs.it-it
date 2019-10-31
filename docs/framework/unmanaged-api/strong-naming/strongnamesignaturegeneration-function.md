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
ms.openlocfilehash: 9ab6fcb64e4654302e411d4dcc587df2e0bf1dc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125185"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="b3c83-102">Funzione StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="b3c83-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="b3c83-103">Genera una firma con nome sicuro per l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="b3c83-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="b3c83-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="b3c83-104">This function has been deprecated.</span></span> <span data-ttu-id="b3c83-105">Usare invece il metodo [ICLRStrongName:: StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b3c83-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3c83-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3c83-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b3c83-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3c83-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b3c83-108">in Percorso del file contenente il manifesto dell'assembly per il quale verrà generata la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b3c83-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="b3c83-109">in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="b3c83-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="b3c83-110">Se `pbKeyBlob` è null, `wszKeyContainer` necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="b3c83-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="b3c83-111">In questo caso, la coppia di chiavi archiviata nel contenitore viene usata per firmare il file.</span><span class="sxs-lookup"><span data-stu-id="b3c83-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="b3c83-112">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.</span><span class="sxs-lookup"><span data-stu-id="b3c83-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="b3c83-113">Le chiavi devono essere chiavi di firma Rivest-Shamir-Adleman (RSA) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="b3c83-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="b3c83-114">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b3c83-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="b3c83-115">in Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="b3c83-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="b3c83-116">Questa coppia è nel formato creato dalla funzione Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="b3c83-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="b3c83-117">Se `pbKeyBlob` è null, si presuppone che il contenitore di chiavi specificato da `wszKeyContainer` contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b3c83-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="b3c83-118">in Dimensione, in byte, del `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="b3c83-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="b3c83-119">out Puntatore alla posizione in cui il Common Language Runtime restituisce la firma.</span><span class="sxs-lookup"><span data-stu-id="b3c83-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="b3c83-120">Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="b3c83-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="b3c83-121">Se `ppbSignatureBlob` non è null, il Common Language Runtime alloca spazio per la restituzione della firma.</span><span class="sxs-lookup"><span data-stu-id="b3c83-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="b3c83-122">Il chiamante deve liberare questo spazio usando la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b3c83-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="b3c83-123">out Dimensione, in byte, della firma restituita.</span><span class="sxs-lookup"><span data-stu-id="b3c83-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3c83-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b3c83-124">Return Value</span></span>  
 <span data-ttu-id="b3c83-125">`true` al completamento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b3c83-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3c83-126">Note</span><span class="sxs-lookup"><span data-stu-id="b3c83-126">Remarks</span></span>  
 <span data-ttu-id="b3c83-127">Specificare null per `wszFilePath` per calcolare le dimensioni della firma senza creare la firma.</span><span class="sxs-lookup"><span data-stu-id="b3c83-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="b3c83-128">La firma può essere archiviata direttamente nel file o restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="b3c83-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="b3c83-129">Se la funzione `StrongNameSignatureGeneration` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="b3c83-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3c83-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3c83-130">Requirements</span></span>  
 <span data-ttu-id="b3c83-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3c83-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3c83-132">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="b3c83-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b3c83-133">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b3c83-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3c83-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3c83-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c83-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3c83-135">See also</span></span>

- [<span data-ttu-id="b3c83-136">Metodo StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="b3c83-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="b3c83-137">Metodo StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="b3c83-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="b3c83-138">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b3c83-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
