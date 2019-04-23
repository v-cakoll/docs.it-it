---
title: Enumerazione CorMethodSemanticsAttr
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e36cb91c3ef741badb04b54e2b62158ecf6ced1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134498"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="5e9d6-102">Enumerazione CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="5e9d6-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="5e9d6-103">Contiene valori che descrivono la relazione tra un metodo e una proprietà o evento associato.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e9d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e9d6-104">Syntax</span></span>  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="5e9d6-105">Membri</span><span class="sxs-lookup"><span data-stu-id="5e9d6-105">Members</span></span>  
  
|<span data-ttu-id="5e9d6-106">Member</span><span class="sxs-lookup"><span data-stu-id="5e9d6-106">Member</span></span>|<span data-ttu-id="5e9d6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e9d6-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="5e9d6-108">Specifica che il metodo è un `set` della funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="5e9d6-109">Specifica che il metodo è un `get` della funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="5e9d6-110">Specifica che il metodo ha una relazione a una proprietà o un evento diverso da quelli definiti qui.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="5e9d6-111">Specifica che il metodo aggiunge i metodi del gestore per un evento.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="5e9d6-112">Specifica il metodo che rimuove i metodi gestore per un evento.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="5e9d6-113">Specifica che il metodo genera un evento.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e9d6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e9d6-114">Requirements</span></span>  
 <span data-ttu-id="5e9d6-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e9d6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e9d6-116">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="5e9d6-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5e9d6-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e9d6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9d6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e9d6-118">See also</span></span>

- [<span data-ttu-id="5e9d6-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="5e9d6-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
