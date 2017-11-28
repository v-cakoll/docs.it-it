---
title: Funzione StrongNameSignatureSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureSize
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureSize
helpviewer_keywords: StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7944763f1c1379228e715b18b563e7aa776fedac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="570fa-102">Funzione StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="570fa-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="570fa-103">Restituisce la dimensione della firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="570fa-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="570fa-104">`StrongNameSignatureSize`è in genere utilizzato dai compilatori per determinare la quantità di spazio da riservare nel file durante la creazione di un assembly con firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="570fa-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="570fa-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="570fa-105">This function has been deprecated.</span></span> <span data-ttu-id="570fa-106">Utilizzare il [:: StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="570fa-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="570fa-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="570fa-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="570fa-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="570fa-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="570fa-109">[in] Una struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi usata per generare la firma nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="570fa-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="570fa-110">[in] Le dimensioni, in byte, di `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="570fa-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="570fa-111">[in] Il numero di byte necessari per archiviare la firma nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="570fa-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="570fa-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="570fa-112">Return Value</span></span>  
 <span data-ttu-id="570fa-113">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="570fa-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="570fa-114">Note</span><span class="sxs-lookup"><span data-stu-id="570fa-114">Remarks</span></span>  
 <span data-ttu-id="570fa-115">Se il `StrongNameSignatureSize` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="570fa-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="570fa-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="570fa-116">Requirements</span></span>  
 <span data-ttu-id="570fa-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="570fa-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="570fa-118">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="570fa-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="570fa-119">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="570fa-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="570fa-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="570fa-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="570fa-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="570fa-121">See Also</span></span>  
 [<span data-ttu-id="570fa-122">StrongNameSignatureSize (metodo)</span><span class="sxs-lookup"><span data-stu-id="570fa-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)  
 [<span data-ttu-id="570fa-123">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="570fa-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
