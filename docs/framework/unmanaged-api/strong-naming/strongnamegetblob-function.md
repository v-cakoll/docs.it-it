---
title: Funzione StrongNameGetBlob
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameGetBlob
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameGetBlob
helpviewer_keywords: StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1948a0d8a8536ebe9b0531eecaf3df446252b0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="212ca-102">Funzione StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="212ca-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="212ca-103">Riempie il buffer specificato con la rappresentazione binaria del file eseguibile all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="212ca-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="212ca-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="212ca-104">This function has been deprecated.</span></span> <span data-ttu-id="212ca-105">Utilizzare il [:: StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="212ca-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="212ca-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="212ca-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="212ca-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="212ca-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="212ca-108">[in] Un percorso valido per il file eseguibile da caricare.</span><span class="sxs-lookup"><span data-stu-id="212ca-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="212ca-109">[in] Buffer in cui caricare il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="212ca-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="212ca-110">[in, out] La richiesta di dimensione massima, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="212ca-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="212ca-111">Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="212ca-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="212ca-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="212ca-112">Return Value</span></span>  
 <span data-ttu-id="212ca-113">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="212ca-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="212ca-114">Note</span><span class="sxs-lookup"><span data-stu-id="212ca-114">Remarks</span></span>  
 <span data-ttu-id="212ca-115">Se il `StrongNameGetBlob` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="212ca-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="212ca-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="212ca-116">Requirements</span></span>  
 <span data-ttu-id="212ca-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="212ca-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="212ca-118">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="212ca-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="212ca-119">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="212ca-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="212ca-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="212ca-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212ca-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="212ca-121">See Also</span></span>  
 [<span data-ttu-id="212ca-122">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="212ca-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="212ca-123">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="212ca-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="212ca-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="212ca-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
