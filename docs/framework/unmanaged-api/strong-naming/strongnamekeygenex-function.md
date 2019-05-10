---
title: Funzione StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 736e537a3f773acbd61dbad013b8dfb7cc429076
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666011"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="071b9-102">Funzione StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="071b9-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="071b9-103">Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata per l'uso di nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="071b9-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="071b9-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="071b9-104">This function has been deprecated.</span></span> <span data-ttu-id="071b9-105">Usare la [StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="071b9-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="071b9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="071b9-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="071b9-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="071b9-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="071b9-108">[in] Il nome di contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="071b9-108">[in] The requested key container name.</span></span> <span data-ttu-id="071b9-109">`wszKeyContainer` deve essere una stringa non vuota, oppure null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="071b9-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="071b9-110">[in] Specifica se mantenere la chiave di registrazione.</span><span class="sxs-lookup"><span data-stu-id="071b9-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="071b9-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="071b9-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="071b9-112">0x00000000 - utilizzato quando `wszKeyContainer` è null per generare un nome di contenitore di chiavi temporanee.</span><span class="sxs-lookup"><span data-stu-id="071b9-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="071b9-113">0x00000001 (`SN_LEAVE_KEY`): Specifica che la chiave deve essere registrata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="071b9-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="071b9-114">[in] Dimensione richiesta della chiave, espressa in bit.</span><span class="sxs-lookup"><span data-stu-id="071b9-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="071b9-115">[out] La coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="071b9-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="071b9-116">[out] Le dimensioni, in byte, di `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="071b9-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="071b9-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="071b9-117">Return Value</span></span>  
 <span data-ttu-id="071b9-118">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="071b9-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="071b9-119">Note</span><span class="sxs-lookup"><span data-stu-id="071b9-119">Remarks</span></span>  
 <span data-ttu-id="071b9-120">Le versioni di .NET Framework 1.0 e 1.1 richiedono un `dwKeySize` pari a 1024 bit per firmare un assembly con nome sicuro; versione 2.0 aggiunge il supporto per le chiavi a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="071b9-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="071b9-121">Una volta recuperata la chiave, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) funzione per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="071b9-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="071b9-122">Se il `StrongNameKeyGenEx` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="071b9-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="071b9-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="071b9-123">Requirements</span></span>  
 <span data-ttu-id="071b9-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="071b9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="071b9-125">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="071b9-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="071b9-126">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="071b9-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="071b9-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="071b9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="071b9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="071b9-128">See also</span></span>

- [<span data-ttu-id="071b9-129">Metodo StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="071b9-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="071b9-130">Metodo StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="071b9-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="071b9-131">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="071b9-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
