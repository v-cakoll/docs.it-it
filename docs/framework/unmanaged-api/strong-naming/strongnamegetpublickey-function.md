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
ms.openlocfilehash: 966a2a628f30f1999688da7b6ba435c1d6cb830c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094657"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="c38d9-102">Funzione StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="c38d9-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="c38d9-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="c38d9-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="c38d9-104">È possibile specificare la coppia di chiavi come nome del contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come raccolta di byte non elaborata.</span><span class="sxs-lookup"><span data-stu-id="c38d9-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="c38d9-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="c38d9-105">This function has been deprecated.</span></span> <span data-ttu-id="c38d9-106">Usare invece il metodo [ICLRStrongName:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c38d9-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c38d9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c38d9-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c38d9-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="c38d9-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="c38d9-109">in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="c38d9-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="c38d9-110">Se `pbKeyBlob` è null, `szKeyContainer` necessario specificare un contenitore valido all'interno del CSP.</span><span class="sxs-lookup"><span data-stu-id="c38d9-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="c38d9-111">In questo caso, `StrongNameGetPublicKey` estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="c38d9-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="c38d9-112">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.</span><span class="sxs-lookup"><span data-stu-id="c38d9-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="c38d9-113">Le chiavi devono essere chiavi di firma Rivest-Shamir-Adleman (RSA) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="c38d9-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="c38d9-114">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="c38d9-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="c38d9-115">in Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="c38d9-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="c38d9-116">Questa coppia è nel formato creato dalla funzione Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="c38d9-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="c38d9-117">Se `pbKeyBlob` è null, si presuppone che il contenitore di chiavi specificato da `szKeyContainer` contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="c38d9-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="c38d9-118">in Dimensione, in byte, del `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="c38d9-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="c38d9-119">out BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="c38d9-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="c38d9-120">Il parametro `ppbPublicKeyBlob` viene allocato dall'Common Language Runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="c38d9-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="c38d9-121">Il chiamante deve liberare la memoria tramite la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="c38d9-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="c38d9-122">out Dimensioni del BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="c38d9-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c38d9-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c38d9-123">Return Value</span></span>  
 <span data-ttu-id="c38d9-124">`true` al completamento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c38d9-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c38d9-125">Note</span><span class="sxs-lookup"><span data-stu-id="c38d9-125">Remarks</span></span>  
 <span data-ttu-id="c38d9-126">La chiave pubblica è contenuta in una struttura [PublicKeyBlob](publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="c38d9-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="c38d9-127">Se la funzione `StrongNameGetPublicKey` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="c38d9-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c38d9-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c38d9-128">Requirements</span></span>  
 <span data-ttu-id="c38d9-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c38d9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c38d9-130">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="c38d9-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c38d9-131">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c38d9-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c38d9-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c38d9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c38d9-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c38d9-133">See also</span></span>

- [<span data-ttu-id="c38d9-134">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="c38d9-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="c38d9-135">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="c38d9-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="c38d9-136">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c38d9-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="c38d9-137">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="c38d9-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
