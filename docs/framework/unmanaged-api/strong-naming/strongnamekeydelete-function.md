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
ms.openlocfilehash: dfc785a48d0cdf1cf2fdc0245a27b8ef35fd2d81
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364515"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="24ce2-102">Funzione StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="24ce2-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="24ce2-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="24ce2-103">Deletes the specified key container.</span></span>

<span data-ttu-id="24ce2-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="24ce2-104">This function has been deprecated.</span></span> <span data-ttu-id="24ce2-105">Usare la [StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="24ce2-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="24ce2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24ce2-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="24ce2-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="24ce2-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="24ce2-108">[in] Il nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="24ce2-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="24ce2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="24ce2-109">Return Value</span></span>

<span data-ttu-id="24ce2-110">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="24ce2-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="24ce2-111">Note</span><span class="sxs-lookup"><span data-stu-id="24ce2-111">Remarks</span></span>

<span data-ttu-id="24ce2-112">Usare la [StrongNameKeyInstall](strongnamekeyinstall-function.md) (funzione) per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="24ce2-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="24ce2-113">Se il `StrongNameKeyDelete` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="24ce2-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="24ce2-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="24ce2-114">Requirements</span></span>

<span data-ttu-id="24ce2-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24ce2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="24ce2-116">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="24ce2-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="24ce2-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="24ce2-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="24ce2-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ce2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="24ce2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24ce2-119">See also</span></span>

- [<span data-ttu-id="24ce2-120">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="24ce2-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="24ce2-121">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="24ce2-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="24ce2-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="24ce2-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)