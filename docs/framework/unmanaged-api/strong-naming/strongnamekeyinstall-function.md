---
title: Funzione StrongNameKeyInstall
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9a8dbc84f375b7bbbad47971936650d81c5c63df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="9dde7-102">Funzione StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="9dde7-102">StrongNameKeyInstall Function</span></span>
<span data-ttu-id="9dde7-103">Importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="9dde7-103">Imports a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="9dde7-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="9dde7-104">This function has been deprecated.</span></span> <span data-ttu-id="9dde7-105">Utilizzare il [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="9dde7-105">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dde7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9dde7-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9dde7-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="9dde7-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="9dde7-108">[in] Il nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="9dde7-108">[in] The name of the key container.</span></span> <span data-ttu-id="9dde7-109">`wszKeyContainer`deve essere una stringa non vuota.</span><span class="sxs-lookup"><span data-stu-id="9dde7-109">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9dde7-110">[in] La coppia di chiavi binaria.</span><span class="sxs-lookup"><span data-stu-id="9dde7-110">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9dde7-111">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="9dde7-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dde7-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9dde7-112">Return Value</span></span>  
 <span data-ttu-id="9dde7-113">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9dde7-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dde7-114">Note</span><span class="sxs-lookup"><span data-stu-id="9dde7-114">Remarks</span></span>  
 <span data-ttu-id="9dde7-115">Utilizzare il [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) funzione per eliminare il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="9dde7-115">Use the [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) function to delete the key container.</span></span>  
  
 <span data-ttu-id="9dde7-116">Se il `StrongNameKeyInstall` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="9dde7-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dde7-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9dde7-117">Requirements</span></span>  
 <span data-ttu-id="9dde7-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dde7-118">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dde7-119">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="9dde7-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9dde7-120">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9dde7-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9dde7-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dde7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dde7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dde7-122">See Also</span></span>  
 [<span data-ttu-id="9dde7-123">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="9dde7-123">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="9dde7-124">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="9dde7-124">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="9dde7-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9dde7-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
