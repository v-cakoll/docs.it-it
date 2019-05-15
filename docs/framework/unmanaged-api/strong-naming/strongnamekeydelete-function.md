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
ms.openlocfilehash: 717d2104db8addf40e5187cee4cc8c46e5dc355e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636732"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="7ac17-102">Funzione StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="7ac17-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="7ac17-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="7ac17-103">Deletes the specified key container.</span></span>

<span data-ttu-id="7ac17-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="7ac17-104">This function has been deprecated.</span></span> <span data-ttu-id="7ac17-105">Usare la [StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="7ac17-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ac17-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ac17-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="7ac17-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ac17-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="7ac17-108">[in] Il nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="7ac17-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="7ac17-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7ac17-109">Return Value</span></span>

<span data-ttu-id="7ac17-110">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7ac17-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ac17-111">Note</span><span class="sxs-lookup"><span data-stu-id="7ac17-111">Remarks</span></span>

<span data-ttu-id="7ac17-112">Usare la [StrongNameKeyInstall](strongnamekeyinstall-function.md) (funzione) per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="7ac17-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="7ac17-113">Se il `StrongNameKeyDelete` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="7ac17-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ac17-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ac17-114">Requirements</span></span>

<span data-ttu-id="7ac17-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ac17-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="7ac17-116">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7ac17-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="7ac17-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7ac17-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="7ac17-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ac17-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7ac17-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ac17-119">See also</span></span>

- [<span data-ttu-id="7ac17-120">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="7ac17-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="7ac17-121">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="7ac17-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="7ac17-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7ac17-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
