---
title: Funzione StrongNameKeyDelete
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a35ec4e3c3110616ac20cd31db134371838deda0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461929"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="4a415-102">Funzione StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="4a415-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="4a415-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="4a415-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="4a415-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="4a415-104">This function has been deprecated.</span></span> <span data-ttu-id="4a415-105">Utilizzare il [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="4a415-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a415-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a415-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a415-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a415-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="4a415-108">[in] Il nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="4a415-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a415-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a415-109">Return Value</span></span>  
 <span data-ttu-id="4a415-110">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4a415-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a415-111">Note</span><span class="sxs-lookup"><span data-stu-id="4a415-111">Remarks</span></span>  
 <span data-ttu-id="4a415-112">Utilizzare il [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) funzione importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="4a415-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="4a415-113">Se il `StrongNameKeyDelete` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="4a415-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a415-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a415-114">Requirements</span></span>  
 <span data-ttu-id="4a415-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a415-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a415-116">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="4a415-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4a415-117">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4a415-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a415-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a415-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a415-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a415-119">See Also</span></span>  
 [<span data-ttu-id="4a415-120">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="4a415-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="4a415-121">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="4a415-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="4a415-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="4a415-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
