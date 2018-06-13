---
title: Funzione StrongNameKeyInstall
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b6760a6418533f5c8f6cec815d86b4cff68aab1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460081"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="6adb3-102">Funzione StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="6adb3-102">StrongNameKeyInstall Function</span></span>
<span data-ttu-id="6adb3-103">Importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="6adb3-103">Imports a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="6adb3-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="6adb3-104">This function has been deprecated.</span></span> <span data-ttu-id="6adb3-105">Utilizzare il [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="6adb3-105">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6adb3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6adb3-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6adb3-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="6adb3-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="6adb3-108">[in] Il nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="6adb3-108">[in] The name of the key container.</span></span> <span data-ttu-id="6adb3-109">`wszKeyContainer` deve essere una stringa non vuota.</span><span class="sxs-lookup"><span data-stu-id="6adb3-109">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="6adb3-110">[in] La coppia di chiavi binaria.</span><span class="sxs-lookup"><span data-stu-id="6adb3-110">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="6adb3-111">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="6adb3-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6adb3-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6adb3-112">Return Value</span></span>  
 <span data-ttu-id="6adb3-113">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="6adb3-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6adb3-114">Note</span><span class="sxs-lookup"><span data-stu-id="6adb3-114">Remarks</span></span>  
 <span data-ttu-id="6adb3-115">Utilizzare il [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) funzione per eliminare il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="6adb3-115">Use the [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) function to delete the key container.</span></span>  
  
 <span data-ttu-id="6adb3-116">Se il `StrongNameKeyInstall` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="6adb3-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6adb3-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6adb3-117">Requirements</span></span>  
 <span data-ttu-id="6adb3-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6adb3-118">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6adb3-119">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="6adb3-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6adb3-120">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6adb3-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6adb3-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6adb3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6adb3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6adb3-122">See Also</span></span>  
 [<span data-ttu-id="6adb3-123">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="6adb3-123">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="6adb3-124">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="6adb3-124">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="6adb3-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6adb3-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
