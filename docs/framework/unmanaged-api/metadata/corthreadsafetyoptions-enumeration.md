---
title: Enumerazione CorThreadSafetyOptions
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 93dd8c56176890d04d792f3c336492e4f232825b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442472"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="6f910-102">Enumerazione CorThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="6f910-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="6f910-103">Specifica i flag per selezionare le opzioni per la thread safety.</span><span class="sxs-lookup"><span data-stu-id="6f910-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f910-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f910-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="6f910-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6f910-105">Members</span></span>

|<span data-ttu-id="6f910-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6f910-106">Member</span></span>|<span data-ttu-id="6f910-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f910-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="6f910-108">Valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="6f910-108">Default value.</span></span> <span data-ttu-id="6f910-109">Uguale a `MDThreadSafetyOff`.</span><span class="sxs-lookup"><span data-stu-id="6f910-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="6f910-110">Indica che non è possibile impostare un blocco di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="6f910-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="6f910-111">Indica che è possibile impostare un blocco in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="6f910-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="6f910-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f910-112">Requirements</span></span>

<span data-ttu-id="6f910-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f910-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6f910-114">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="6f910-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="6f910-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f910-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6f910-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f910-116">See also</span></span>

- [<span data-ttu-id="6f910-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="6f910-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
