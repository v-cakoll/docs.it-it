---
title: Funzione StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a465b38951593fea7f36ef4ffba32e282f079f77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533598"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="8fed8-102">Funzione StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="8fed8-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="8fed8-103">Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="8fed8-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="8fed8-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="8fed8-104">This function has been deprecated.</span></span> <span data-ttu-id="8fed8-105">Usare la [StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="8fed8-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fed8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fed8-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fed8-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fed8-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8fed8-108">[in] Un percorso valido per il file eseguibile da caricare.</span><span class="sxs-lookup"><span data-stu-id="8fed8-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="8fed8-109">[in] Buffer in cui caricare il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="8fed8-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="8fed8-110">[in, out] La massima dimensione, espressa in byte, richiesta del `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="8fed8-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="8fed8-111">Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="8fed8-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fed8-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8fed8-112">Return Value</span></span>  
 <span data-ttu-id="8fed8-113">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="8fed8-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fed8-114">Note</span><span class="sxs-lookup"><span data-stu-id="8fed8-114">Remarks</span></span>  
 <span data-ttu-id="8fed8-115">Se il `StrongNameGetBlob` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="8fed8-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fed8-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8fed8-116">Requirements</span></span>  
 <span data-ttu-id="8fed8-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fed8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fed8-118">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8fed8-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8fed8-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8fed8-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8fed8-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fed8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fed8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fed8-121">See also</span></span>
- [<span data-ttu-id="8fed8-122">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="8fed8-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="8fed8-123">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="8fed8-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="8fed8-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8fed8-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
