---
title: Funzione StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dac6f2ca813f3b8cbed48d540a991e6396edf679
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495221"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="52967-102">Funzione StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="52967-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="52967-103">Restituisce le dimensioni della firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="52967-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="52967-104">`StrongNameSignatureSize` è in genere utilizzata dai compilatori per determinare la quantità di spazio da riservare nel file durante la creazione di un assembly con firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="52967-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="52967-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="52967-105">This function has been deprecated.</span></span> <span data-ttu-id="52967-106">Usare la [StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="52967-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52967-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52967-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="52967-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="52967-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="52967-109">[in] Una struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi usata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="52967-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="52967-110">[in] Le dimensioni, in byte, di `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="52967-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="52967-111">[in] Il numero di byte necessari per archiviare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="52967-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52967-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="52967-112">Return Value</span></span>  
 <span data-ttu-id="52967-113">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="52967-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52967-114">Note</span><span class="sxs-lookup"><span data-stu-id="52967-114">Remarks</span></span>  
 <span data-ttu-id="52967-115">Se il `StrongNameSignatureSize` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="52967-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52967-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52967-116">Requirements</span></span>  
 <span data-ttu-id="52967-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52967-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52967-118">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="52967-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="52967-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="52967-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52967-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52967-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52967-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52967-121">See also</span></span>
- [<span data-ttu-id="52967-122">Metodo StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="52967-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="52967-123">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="52967-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
