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
ms.openlocfilehash: af75a645b11325b96740807f9a3df65f5a676026
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120857"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="3d554-102">Funzione StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="3d554-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="3d554-103">Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata per l'uso di nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="3d554-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="3d554-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="3d554-104">This function has been deprecated.</span></span> <span data-ttu-id="3d554-105">Usare la [StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="3d554-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d554-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d554-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d554-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d554-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="3d554-108">[in] Il nome di contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="3d554-108">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="3d554-109">deve essere una stringa non vuota, oppure null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="3d554-109">must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3d554-110">[in] Specifica se mantenere la chiave di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3d554-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="3d554-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d554-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="3d554-112">0x00000000 - utilizzato quando `wszKeyContainer` è null per generare un nome di contenitore di chiavi temporanee.</span><span class="sxs-lookup"><span data-stu-id="3d554-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="3d554-113">0x00000001 (`SN_LEAVE_KEY`): Specifica che la chiave deve essere registrata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="3d554-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="3d554-114">[in] Dimensione richiesta della chiave, espressa in bit.</span><span class="sxs-lookup"><span data-stu-id="3d554-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="3d554-115">[out] La coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="3d554-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="3d554-116">[out] Le dimensioni, in byte, di `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="3d554-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d554-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3d554-117">Return Value</span></span>  
 `true` <span data-ttu-id="3d554-118">al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3d554-118">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d554-119">Note</span><span class="sxs-lookup"><span data-stu-id="3d554-119">Remarks</span></span>  
 <span data-ttu-id="3d554-120">Le versioni di .NET Framework 1.0 e 1.1 richiedono un `dwKeySize` pari a 1024 bit per firmare un assembly con nome sicuro; versione 2.0 aggiunge il supporto per le chiavi a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="3d554-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="3d554-121">Una volta recuperata la chiave, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) funzione per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="3d554-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="3d554-122">Se il `StrongNameKeyGenEx` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="3d554-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d554-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d554-123">Requirements</span></span>  
 <span data-ttu-id="3d554-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d554-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d554-125">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="3d554-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3d554-126">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3d554-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3d554-127">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3d554-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d554-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d554-128">See also</span></span>

- [<span data-ttu-id="3d554-129">Metodo StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="3d554-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="3d554-130">Metodo StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="3d554-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="3d554-131">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3d554-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
