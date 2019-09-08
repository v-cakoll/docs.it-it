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
ms.openlocfilehash: 89398c221dcf9d6f89027f15da4062bc7ed67e3f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798979"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="0c0f6-102">Funzione StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="0c0f6-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="0c0f6-103">Genera una firma con nome sicuro per l'assembly specificato, in base ai flag specificati.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="0c0f6-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-104">This function has been deprecated.</span></span> <span data-ttu-id="0c0f6-105">Usare invece il metodo [ICLRStrongName:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0c0f6-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c0f6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c0f6-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="0c0f6-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c0f6-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0c0f6-108">in Percorso del file contenente il manifesto dell'assembly per il quale verrà generata la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="0c0f6-109">in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="0c0f6-110">Se `pbKeyBlob` è null, `wszKeyContainer` è necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP).</span><span class="sxs-lookup"><span data-stu-id="0c0f6-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="0c0f6-111">In questo caso, la coppia di chiavi archiviata nel contenitore viene usata per firmare il file.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="0c0f6-112">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="0c0f6-113">in Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="0c0f6-114">Questa coppia è nel formato creato dalla funzione Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="0c0f6-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="0c0f6-115">Se `pbKeyBlob` è null, si presuppone che il contenitore `wszKeyContainer` di chiavi specificato da contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="0c0f6-116">in Dimensione, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="0c0f6-117">out Puntatore alla posizione in cui il Common Language Runtime restituisce la firma.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="0c0f6-118">Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="0c0f6-119">Se `ppbSignatureBlob` non è null, il Common Language Runtime alloca spazio per la restituzione della firma.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="0c0f6-120">Il chiamante deve liberare questo spazio usando la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="0c0f6-120">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="0c0f6-121">out Dimensione, in byte, della firma restituita.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0c0f6-122">in Uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c0f6-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="0c0f6-123">`SN_SIGN_ALL_FILES`(0x00000001): Ricalcola tutti gli hash per i moduli collegati.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="0c0f6-124">`SN_TEST_SIGN`(0x00000002)-test-firma l'assembly.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c0f6-125">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c0f6-125">Return Value</span></span>  
 <span data-ttu-id="0c0f6-126">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c0f6-127">Note</span><span class="sxs-lookup"><span data-stu-id="0c0f6-127">Remarks</span></span>  
 <span data-ttu-id="0c0f6-128">Specificare null per `wszFilePath` per calcolare le dimensioni della firma senza creare la firma.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="0c0f6-129">La firma può essere archiviata direttamente nel file o restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="0c0f6-130">Se `SN_SIGN_ALL_FILES` viene specificato, ma non è inclusa una chiave pubblica ( `pbKeyBlob` sia `wszFilePath` che sono null), gli hash per i moduli collegati vengono ricalcolati, ma l'assembly non viene firmato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="0c0f6-131">Se `SN_TEST_SIGN` si specifica, l'intestazione Common Language Runtime non viene modificata per indicare che l'assembly è firmato con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="0c0f6-132">Se la `StrongNameSignatureGenerationEx` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="0c0f6-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c0f6-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c0f6-133">Requirements</span></span>  
 <span data-ttu-id="0c0f6-134">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c0f6-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c0f6-135">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="0c0f6-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0c0f6-136">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0c0f6-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c0f6-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c0f6-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0f6-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c0f6-138">See also</span></span>

- [<span data-ttu-id="0c0f6-139">Metodo StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="0c0f6-139">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="0c0f6-140">Metodo StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="0c0f6-140">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="0c0f6-141">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="0c0f6-141">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
