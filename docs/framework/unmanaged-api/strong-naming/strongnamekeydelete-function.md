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
ms.openlocfilehash: d37f990241ae704abef55d863da0f40a31284837
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141590"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="509d6-102">Funzione StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="509d6-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="509d6-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="509d6-103">Deletes the specified key container.</span></span>

<span data-ttu-id="509d6-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="509d6-104">This function has been deprecated.</span></span> <span data-ttu-id="509d6-105">Usare invece il metodo [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="509d6-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="509d6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="509d6-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="509d6-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="509d6-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="509d6-108">in Nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="509d6-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="509d6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="509d6-109">Return Value</span></span>

<span data-ttu-id="509d6-110">`true` al completamento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="509d6-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="509d6-111">Note</span><span class="sxs-lookup"><span data-stu-id="509d6-111">Remarks</span></span>

<span data-ttu-id="509d6-112">Usare la funzione [StrongNameKeyInstall](strongnamekeyinstall-function.md) per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="509d6-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="509d6-113">Se la funzione `StrongNameKeyDelete` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="509d6-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="509d6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="509d6-114">Requirements</span></span>

<span data-ttu-id="509d6-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="509d6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="509d6-116">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="509d6-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="509d6-117">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="509d6-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="509d6-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="509d6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="509d6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="509d6-119">See also</span></span>

- [<span data-ttu-id="509d6-120">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="509d6-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="509d6-121">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="509d6-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="509d6-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="509d6-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
