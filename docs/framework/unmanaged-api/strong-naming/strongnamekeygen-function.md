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
ms.openlocfilehash: f062f47790136e8cd39c6751b7c75eef660c2b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799143"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="59442-102">Funzione StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="59442-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="59442-103">Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="59442-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="59442-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="59442-104">This function has been deprecated.</span></span> <span data-ttu-id="59442-105">Usare invece il metodo [ICLRStrongName:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) .</span><span class="sxs-lookup"><span data-stu-id="59442-105">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59442-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59442-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59442-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="59442-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="59442-108">in Nome del contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="59442-108">[in] The requested key container name.</span></span> <span data-ttu-id="59442-109">`wszKeyContainer`deve essere una stringa non vuota o null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="59442-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="59442-110">in Specifica se lasciare la chiave registrata.</span><span class="sxs-lookup"><span data-stu-id="59442-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="59442-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="59442-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="59442-112">0x00000000: viene usato `wszKeyContainer` quando è null per generare un nome del contenitore di chiavi temporaneo.</span><span class="sxs-lookup"><span data-stu-id="59442-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="59442-113">0x00000001 (`SN_LEAVE_KEY`): specifica che la chiave deve essere lasciata registrata.</span><span class="sxs-lookup"><span data-stu-id="59442-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="59442-114">out Coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="59442-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="59442-115">out Dimensione, in byte, di `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="59442-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59442-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="59442-116">Return Value</span></span>  
 <span data-ttu-id="59442-117">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="59442-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59442-118">Note</span><span class="sxs-lookup"><span data-stu-id="59442-118">Remarks</span></span>  
 <span data-ttu-id="59442-119">La `StrongNameKeyGen` funzione crea una chiave a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="59442-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="59442-120">Dopo che la chiave è stata recuperata, è necessario chiamare la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="59442-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="59442-121">Se la `StrongNameKeyGen` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="59442-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59442-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59442-122">Requirements</span></span>  
 <span data-ttu-id="59442-123">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59442-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59442-124">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="59442-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="59442-125">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="59442-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59442-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59442-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59442-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59442-127">See also</span></span>

- [<span data-ttu-id="59442-128">Metodo StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="59442-128">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="59442-129">Metodo StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="59442-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="59442-130">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="59442-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
