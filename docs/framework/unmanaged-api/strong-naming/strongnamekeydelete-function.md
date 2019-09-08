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
ms.openlocfilehash: 17d35193f69966e02ac5e483924fcb3ee2e06758
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799028"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="a273e-102">Funzione StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="a273e-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="a273e-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="a273e-103">Deletes the specified key container.</span></span>

<span data-ttu-id="a273e-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="a273e-104">This function has been deprecated.</span></span> <span data-ttu-id="a273e-105">Usare invece il metodo [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a273e-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="a273e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a273e-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="a273e-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a273e-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="a273e-108">in Nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="a273e-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="a273e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a273e-109">Return Value</span></span>

<span data-ttu-id="a273e-110">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="a273e-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a273e-111">Note</span><span class="sxs-lookup"><span data-stu-id="a273e-111">Remarks</span></span>

<span data-ttu-id="a273e-112">Usare la funzione [StrongNameKeyInstall](strongnamekeyinstall-function.md) per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="a273e-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="a273e-113">Se la `StrongNameKeyDelete` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="a273e-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="a273e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a273e-114">Requirements</span></span>

<span data-ttu-id="a273e-115">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a273e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a273e-116">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="a273e-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="a273e-117">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a273e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="a273e-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a273e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a273e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a273e-119">See also</span></span>

- [<span data-ttu-id="a273e-120">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="a273e-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="a273e-121">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="a273e-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="a273e-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a273e-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
