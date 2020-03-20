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
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176929"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="47c56-102">Funzione StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="47c56-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="47c56-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="47c56-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="47c56-104">La coppia di chiavi può essere fornita come nome del contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come raccolta non elaborata di byte.</span><span class="sxs-lookup"><span data-stu-id="47c56-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="47c56-105">Questa funzione è deprecata.</span><span class="sxs-lookup"><span data-stu-id="47c56-105">This function has been deprecated.</span></span> <span data-ttu-id="47c56-106">Utilizzare invece il metodo [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) .</span><span class="sxs-lookup"><span data-stu-id="47c56-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c56-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47c56-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47c56-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="47c56-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="47c56-109">[in] Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="47c56-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="47c56-110">Se `pbKeyBlob` è `szKeyContainer` null, è necessario specificare un contenitore valido all'interno del CSP.</span><span class="sxs-lookup"><span data-stu-id="47c56-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="47c56-111">In questo `StrongNameGetPublicKey` caso, estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="47c56-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="47c56-112">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nell'oggetto binario di grandi dimensioni chiave (BLOB).</span><span class="sxs-lookup"><span data-stu-id="47c56-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="47c56-113">Le chiavi devono essere chiavi di firma RSA (Rivest-Shamir-Adleman) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="47c56-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="47c56-114">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="47c56-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="47c56-115">[in] Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="47c56-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="47c56-116">Questa coppia è nel formato creato `CryptExportKey` dalla funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="47c56-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="47c56-117">Se `pbKeyBlob` è null, si `szKeyContainer` presuppone che il contenitore di chiavi specificato da contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="47c56-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="47c56-118">[in] Dimensione, in byte, `pbKeyBlob`di .</span><span class="sxs-lookup"><span data-stu-id="47c56-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="47c56-119">[fuori] BLOB della chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="47c56-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="47c56-120">Il `ppbPublicKeyBlob` parametro viene allocato da Common Language Runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="47c56-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="47c56-121">Il chiamante deve liberare la memoria utilizzando la funzione [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)</span><span class="sxs-lookup"><span data-stu-id="47c56-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="47c56-122">[fuori] Dimensione del BLOB della chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="47c56-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47c56-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="47c56-123">Return Value</span></span>  
 <span data-ttu-id="47c56-124">`true`al termine del successo; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="47c56-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47c56-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="47c56-125">Remarks</span></span>  
 <span data-ttu-id="47c56-126">La chiave pubblica è contenuta in una struttura [PublicKeyBlob.The public](publickeyblob-structure.md) key is contained in a PublicKeyBlob structure.</span><span class="sxs-lookup"><span data-stu-id="47c56-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="47c56-127">Se `StrongNameGetPublicKey` la funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="47c56-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c56-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47c56-128">Requirements</span></span>  
 <span data-ttu-id="47c56-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47c56-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47c56-130">**Intestazione:** NomeForte.h</span><span class="sxs-lookup"><span data-stu-id="47c56-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="47c56-131">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47c56-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47c56-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47c56-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c56-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47c56-133">See also</span></span>

- [<span data-ttu-id="47c56-134">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="47c56-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="47c56-135">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="47c56-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="47c56-136">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="47c56-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="47c56-137">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="47c56-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
