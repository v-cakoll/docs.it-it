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
ms.openlocfilehash: f716ff35ae0cd3d2a53c55756b8957e54fa355c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431535"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="83dd8-102">Struttura IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="83dd8-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="83dd8-103">Contiene informazioni sugli attributi di metadati su un [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="83dd8-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83dd8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83dd8-104">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="83dd8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="83dd8-105">Members</span></span>  
  
|<span data-ttu-id="83dd8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="83dd8-106">Member</span></span>|<span data-ttu-id="83dd8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83dd8-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="83dd8-108">Un puntatore a una stringa di caratteri con terminazione null che contiene lo spazio dei nomi cui è l'attributo.</span><span class="sxs-lookup"><span data-stu-id="83dd8-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="83dd8-109">Un puntatore a una stringa di caratteri con terminazione null che contiene il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="83dd8-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="83dd8-110">Un puntatore a una stringa di caratteri con terminazione null che contiene il valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="83dd8-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83dd8-111">Note</span><span class="sxs-lookup"><span data-stu-id="83dd8-111">Remarks</span></span>  
 <span data-ttu-id="83dd8-112">Il `IDENTITY_ATTRIBUTE` struttura contiene tre puntatori alle stringhe di caratteri con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="83dd8-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="83dd8-113">Queste tre stringhe descrivono un attributo.</span><span class="sxs-lookup"><span data-stu-id="83dd8-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="83dd8-114">Un'istanza di un `IDENTITY_ATTRIBUTE` struttura è associata a un'istanza di un [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="83dd8-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="83dd8-115">Il `IDENTITY_ATTRIBUTE` struttura contiene le stringhe effettive e i corrispondenti `IDENTITY_ATTRIBUTE_BLOB` struttura sono elencati gli offset alle tre stringhe elencate nella `IDENTITY_ATTRIBUTE` struttura.</span><span class="sxs-lookup"><span data-stu-id="83dd8-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83dd8-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83dd8-116">Requirements</span></span>  
 <span data-ttu-id="83dd8-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83dd8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83dd8-118">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="83dd8-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="83dd8-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83dd8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83dd8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83dd8-120">See Also</span></span>  
 [<span data-ttu-id="83dd8-121">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="83dd8-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [<span data-ttu-id="83dd8-122">Struttura IDENTITY_ATTRIBUTE_BLOB</span><span class="sxs-lookup"><span data-stu-id="83dd8-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [<span data-ttu-id="83dd8-123">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="83dd8-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
