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
ms.openlocfilehash: 5e65e962d099e944fe243b3acc0a7c25a3bb960c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458670"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="1d2d8-102">Funzione StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="1d2d8-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="1d2d8-103">Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata, per l'utilizzo con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="1d2d8-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-104">This function has been deprecated.</span></span> <span data-ttu-id="1d2d8-105">Utilizzare il [:: StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d2d8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d2d8-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d2d8-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1d2d8-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="1d2d8-108">[in] Il nome di contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-108">[in] The requested key container name.</span></span> <span data-ttu-id="1d2d8-109">`wszKeyContainer` deve essere una stringa non vuota o null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1d2d8-110">[in] Specifica se mantenere la chiave registrata.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="1d2d8-111">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="1d2d8-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="1d2d8-112">0x00000000 - utilizzato quando `wszKeyContainer` è null per generare un nome di contenitore di chiavi temporaneo.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="1d2d8-113">0x00000001 (`SN_LEAVE_KEY`)-specifica che la chiave deve essere registrata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="1d2d8-114">[in] La dimensione richiesta della chiave in bit.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="1d2d8-115">[out] La coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="1d2d8-116">[out] Le dimensioni, in byte, di `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d2d8-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1d2d8-117">Return Value</span></span>  
 <span data-ttu-id="1d2d8-118">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d2d8-119">Note</span><span class="sxs-lookup"><span data-stu-id="1d2d8-119">Remarks</span></span>  
 <span data-ttu-id="1d2d8-120">Le versioni di .NET Framework 1.0 e 1.1 richiedono un `dwKeySize` pari a 1024 bit per firmare un assembly con un nome sicuro; versione 2.0 include il supporto per le chiavi a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="1d2d8-121">Dopo il recupero della chiave, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) funzione per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="1d2d8-122">Se il `StrongNameKeyGenEx` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="1d2d8-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d2d8-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d2d8-123">Requirements</span></span>  
 <span data-ttu-id="1d2d8-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d2d8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d2d8-125">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="1d2d8-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1d2d8-126">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1d2d8-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d2d8-127">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d2d8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2d8-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d2d8-128">See Also</span></span>  
 [<span data-ttu-id="1d2d8-129">Metodo StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="1d2d8-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [<span data-ttu-id="1d2d8-130">Metodo StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="1d2d8-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="1d2d8-131">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="1d2d8-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
