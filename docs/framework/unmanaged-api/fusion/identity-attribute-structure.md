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
ms.openlocfilehash: 8b7edf1cc642228c4a79c855b51727264f31741c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107978"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="6fde1-102">Struttura IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="6fde1-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="6fde1-103">Contiene informazioni sugli attributi di metadati relativi a un'istanza di [IDefinitionIdentity](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6fde1-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fde1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fde1-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="6fde1-105">Members</span><span class="sxs-lookup"><span data-stu-id="6fde1-105">Members</span></span>  
  
|<span data-ttu-id="6fde1-106">Member</span><span class="sxs-lookup"><span data-stu-id="6fde1-106">Member</span></span>|<span data-ttu-id="6fde1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fde1-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="6fde1-108">Puntatore a una stringa di caratteri con terminazione null che contiene lo spazio dei nomi in cui si trova l'attributo.</span><span class="sxs-lookup"><span data-stu-id="6fde1-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="6fde1-109">Puntatore a una stringa di caratteri con terminazione null che contiene il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="6fde1-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="6fde1-110">Puntatore a una stringa di caratteri con terminazione null che contiene il valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="6fde1-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fde1-111">Note</span><span class="sxs-lookup"><span data-stu-id="6fde1-111">Remarks</span></span>  
 <span data-ttu-id="6fde1-112">La struttura `IDENTITY_ATTRIBUTE` contiene tre puntatori a stringhe di caratteri con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="6fde1-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="6fde1-113">Queste tre stringhe descrivono un attributo.</span><span class="sxs-lookup"><span data-stu-id="6fde1-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="6fde1-114">Un'istanza di una struttura `IDENTITY_ATTRIBUTE` è associata a un'istanza di una struttura [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="6fde1-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="6fde1-115">La struttura di `IDENTITY_ATTRIBUTE` contiene le stringhe effettive e la struttura `IDENTITY_ATTRIBUTE_BLOB` corrispondente elenca gli offset alle tre stringhe elencate nella struttura `IDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="6fde1-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fde1-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6fde1-116">Requirements</span></span>  
 <span data-ttu-id="6fde1-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fde1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fde1-118">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="6fde1-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6fde1-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fde1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fde1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fde1-120">See also</span></span>

- [<span data-ttu-id="6fde1-121">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="6fde1-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="6fde1-122">Struttura IDENTITY_ATTRIBUTE_BLOB</span><span class="sxs-lookup"><span data-stu-id="6fde1-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="6fde1-123">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="6fde1-123">Fusion Structures</span></span>](fusion-structures.md)
