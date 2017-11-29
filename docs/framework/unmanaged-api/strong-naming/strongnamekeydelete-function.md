---
title: Funzione StrongNameKeyDelete
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyDelete
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyDelete
helpviewer_keywords: StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c7b3ccc9ec1b8cbc81de115f734e1d11e0e0ae0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="2fabe-102">Funzione StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="2fabe-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="2fabe-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="2fabe-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="2fabe-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="2fabe-104">This function has been deprecated.</span></span> <span data-ttu-id="2fabe-105">Utilizzare il [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="2fabe-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fabe-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2fabe-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2fabe-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="2fabe-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="2fabe-108">[in] Il nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="2fabe-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fabe-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2fabe-109">Return Value</span></span>  
 <span data-ttu-id="2fabe-110">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2fabe-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fabe-111">Note</span><span class="sxs-lookup"><span data-stu-id="2fabe-111">Remarks</span></span>  
 <span data-ttu-id="2fabe-112">Utilizzare il [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) funzione importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fabe-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="2fabe-113">Se il `StrongNameKeyDelete` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="2fabe-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fabe-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2fabe-114">Requirements</span></span>  
 <span data-ttu-id="2fabe-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fabe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fabe-116">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="2fabe-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2fabe-117">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2fabe-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2fabe-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fabe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fabe-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fabe-119">See Also</span></span>  
 [<span data-ttu-id="2fabe-120">StrongNameKeyDelete (metodo)</span><span class="sxs-lookup"><span data-stu-id="2fabe-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="2fabe-121">StrongNameKeyInstall (metodo)</span><span class="sxs-lookup"><span data-stu-id="2fabe-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="2fabe-122">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2fabe-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
