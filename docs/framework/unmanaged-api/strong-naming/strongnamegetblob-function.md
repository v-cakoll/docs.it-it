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
ms.openlocfilehash: e23232b55a841672ee193b980c310995ba688e00
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160992"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="61fa3-102">Funzione StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="61fa3-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="61fa3-103">Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="61fa3-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="61fa3-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="61fa3-104">This function has been deprecated.</span></span> <span data-ttu-id="61fa3-105">Usare la [StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="61fa3-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61fa3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61fa3-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61fa3-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="61fa3-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="61fa3-108">[in] Un percorso valido per il file eseguibile da caricare.</span><span class="sxs-lookup"><span data-stu-id="61fa3-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="61fa3-109">[in] Buffer in cui caricare il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="61fa3-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="61fa3-110">[in, out] La massima dimensione, espressa in byte, richiesta del `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="61fa3-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="61fa3-111">Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="61fa3-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61fa3-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="61fa3-112">Return Value</span></span>  
 `true` <span data-ttu-id="61fa3-113">al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="61fa3-113">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61fa3-114">Note</span><span class="sxs-lookup"><span data-stu-id="61fa3-114">Remarks</span></span>  
 <span data-ttu-id="61fa3-115">Se il `StrongNameGetBlob` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="61fa3-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61fa3-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61fa3-116">Requirements</span></span>  
 <span data-ttu-id="61fa3-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61fa3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61fa3-118">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="61fa3-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="61fa3-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="61fa3-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="61fa3-120">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="61fa3-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61fa3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61fa3-121">See also</span></span>

- [<span data-ttu-id="61fa3-122">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="61fa3-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="61fa3-123">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="61fa3-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="61fa3-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="61fa3-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
