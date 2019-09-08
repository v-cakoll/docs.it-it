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
ms.openlocfilehash: f9ab908866402bd7a883114466f32921321a5ee6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799008"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="e7e91-102">Funzione StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="e7e91-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="e7e91-103">Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata, per l'uso del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e7e91-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="e7e91-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="e7e91-104">This function has been deprecated.</span></span> <span data-ttu-id="e7e91-105">Usare invece il metodo [ICLRStrongName:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e7e91-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e91-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7e91-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7e91-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7e91-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="e7e91-108">in Nome del contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="e7e91-108">[in] The requested key container name.</span></span> <span data-ttu-id="e7e91-109">`wszKeyContainer`deve essere una stringa non vuota o null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="e7e91-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e7e91-110">in Specifica se lasciare la chiave registrata.</span><span class="sxs-lookup"><span data-stu-id="e7e91-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="e7e91-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7e91-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="e7e91-112">0x00000000: viene usato `wszKeyContainer` quando è null per generare un nome del contenitore di chiavi temporaneo.</span><span class="sxs-lookup"><span data-stu-id="e7e91-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="e7e91-113">0x00000001 (`SN_LEAVE_KEY`): specifica che la chiave deve essere lasciata registrata.</span><span class="sxs-lookup"><span data-stu-id="e7e91-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="e7e91-114">in Dimensioni richieste della chiave, in bit.</span><span class="sxs-lookup"><span data-stu-id="e7e91-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="e7e91-115">out Coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="e7e91-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="e7e91-116">out Dimensione, in byte, di `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="e7e91-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7e91-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e7e91-117">Return Value</span></span>  
 <span data-ttu-id="e7e91-118">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="e7e91-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7e91-119">Note</span><span class="sxs-lookup"><span data-stu-id="e7e91-119">Remarks</span></span>  
 <span data-ttu-id="e7e91-120">Per la firma di un assembly con un `dwKeySize` nome sicuro, le versioni di .NET Framework 1,0 e 1,1 richiedono un valore di 1024 bit. la versione 2,0 aggiunge i supporti per le chiavi a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="e7e91-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="e7e91-121">Dopo che la chiave è stata recuperata, è necessario chiamare la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="e7e91-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="e7e91-122">Se la `StrongNameKeyGenEx` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="e7e91-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e91-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7e91-123">Requirements</span></span>  
 <span data-ttu-id="e7e91-124">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7e91-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e91-125">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e7e91-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e7e91-126">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e7e91-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7e91-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e91-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e91-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7e91-128">See also</span></span>

- [<span data-ttu-id="e7e91-129">Metodo StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="e7e91-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="e7e91-130">Metodo StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="e7e91-130">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="e7e91-131">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e7e91-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
