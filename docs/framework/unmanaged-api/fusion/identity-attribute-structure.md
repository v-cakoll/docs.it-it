---
title: Struttura IDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796494"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="be31d-102">Struttura IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="be31d-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="be31d-103">Contiene informazioni sugli attributi di metadati relativi a un'istanza di [IDefinitionIdentity](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="be31d-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be31d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be31d-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="be31d-105">Members</span><span class="sxs-lookup"><span data-stu-id="be31d-105">Members</span></span>  
  
|<span data-ttu-id="be31d-106">Member</span><span class="sxs-lookup"><span data-stu-id="be31d-106">Member</span></span>|<span data-ttu-id="be31d-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="be31d-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="be31d-108">Puntatore a una stringa di caratteri con terminazione null che contiene lo spazio dei nomi in cui si trova l'attributo.</span><span class="sxs-lookup"><span data-stu-id="be31d-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="be31d-109">Puntatore a una stringa di caratteri con terminazione null che contiene il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="be31d-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="be31d-110">Puntatore a una stringa di caratteri con terminazione null che contiene il valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="be31d-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be31d-111">Note</span><span class="sxs-lookup"><span data-stu-id="be31d-111">Remarks</span></span>  
 <span data-ttu-id="be31d-112">La `IDENTITY_ATTRIBUTE` struttura contiene tre puntatori a stringhe di caratteri con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="be31d-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="be31d-113">Queste tre stringhe descrivono un attributo.</span><span class="sxs-lookup"><span data-stu-id="be31d-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="be31d-114">Un'istanza di una `IDENTITY_ATTRIBUTE` struttura è associata a un'istanza di una struttura [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="be31d-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="be31d-115">La `IDENTITY_ATTRIBUTE` struttura contiene le stringhe effettive e la struttura `IDENTITY_ATTRIBUTE_BLOB` corrispondente elenca gli offset alle `IDENTITY_ATTRIBUTE` tre stringhe elencate nella struttura.</span><span class="sxs-lookup"><span data-stu-id="be31d-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be31d-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be31d-116">Requirements</span></span>  
 <span data-ttu-id="be31d-117">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be31d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be31d-118">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="be31d-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="be31d-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be31d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be31d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be31d-120">See also</span></span>

- [<span data-ttu-id="be31d-121">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="be31d-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="be31d-122">Struttura IDENTITY_ATTRIBUTE_BLOB</span><span class="sxs-lookup"><span data-stu-id="be31d-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="be31d-123">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="be31d-123">Fusion Structures</span></span>](fusion-structures.md)
