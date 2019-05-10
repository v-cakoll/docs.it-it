---
title: Funzione StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95c1d8171d2d76ecf085252e7973c0da851b3225
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666035"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="36b52-102">Funzione StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="36b52-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="36b52-103">Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="36b52-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="36b52-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="36b52-104">This function has been deprecated.</span></span> <span data-ttu-id="36b52-105">Usare la [StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="36b52-105">Use the [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36b52-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36b52-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36b52-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="36b52-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="36b52-108">[in] Il nome di contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="36b52-108">[in] The requested key container name.</span></span> <span data-ttu-id="36b52-109">`wszKeyContainer` deve essere una stringa non vuota, oppure null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="36b52-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="36b52-110">[in] Specifica se mantenere la chiave di registrazione.</span><span class="sxs-lookup"><span data-stu-id="36b52-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="36b52-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="36b52-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="36b52-112">0x00000000 - utilizzato quando `wszKeyContainer` è null per generare un nome di contenitore di chiavi temporanee.</span><span class="sxs-lookup"><span data-stu-id="36b52-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="36b52-113">0x00000001 (`SN_LEAVE_KEY`): Specifica che la chiave deve essere registrata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="36b52-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="36b52-114">[out] La coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="36b52-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="36b52-115">[out] Le dimensioni, in byte, di `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="36b52-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36b52-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="36b52-116">Return Value</span></span>  
 <span data-ttu-id="36b52-117">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="36b52-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36b52-118">Note</span><span class="sxs-lookup"><span data-stu-id="36b52-118">Remarks</span></span>  
 <span data-ttu-id="36b52-119">Il `StrongNameKeyGen` funzione crea una chiave a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="36b52-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="36b52-120">Una volta recuperata la chiave, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) funzione per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="36b52-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="36b52-121">Se il `StrongNameKeyGen` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="36b52-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36b52-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36b52-122">Requirements</span></span>  
 <span data-ttu-id="36b52-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36b52-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36b52-124">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="36b52-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="36b52-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="36b52-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36b52-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36b52-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b52-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36b52-127">See also</span></span>

- [<span data-ttu-id="36b52-128">Metodo StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="36b52-128">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="36b52-129">Metodo StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="36b52-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="36b52-130">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="36b52-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
