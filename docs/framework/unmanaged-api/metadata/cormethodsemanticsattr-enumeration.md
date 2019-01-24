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
ms.openlocfilehash: f888c39160e52e550d07f58b9c5bcd11fd625658
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564081"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="66a5c-102">Enumerazione CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="66a5c-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="66a5c-103">Contiene valori che descrivono la relazione tra un metodo e una proprietà o evento associato.</span><span class="sxs-lookup"><span data-stu-id="66a5c-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66a5c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66a5c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="66a5c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="66a5c-105">Members</span></span>  
  
|<span data-ttu-id="66a5c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="66a5c-106">Member</span></span>|<span data-ttu-id="66a5c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66a5c-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="66a5c-108">Specifica che il metodo è un `set` della funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="66a5c-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="66a5c-109">Specifica che il metodo è un `get` della funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="66a5c-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="66a5c-110">Specifica che il metodo ha una relazione a una proprietà o un evento diverso da quelli definiti qui.</span><span class="sxs-lookup"><span data-stu-id="66a5c-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="66a5c-111">Specifica che il metodo aggiunge i metodi del gestore per un evento.</span><span class="sxs-lookup"><span data-stu-id="66a5c-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="66a5c-112">Specifica il metodo che rimuove i metodi gestore per un evento.</span><span class="sxs-lookup"><span data-stu-id="66a5c-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="66a5c-113">Specifica che il metodo genera un evento.</span><span class="sxs-lookup"><span data-stu-id="66a5c-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66a5c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="66a5c-114">Requirements</span></span>  
 <span data-ttu-id="66a5c-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66a5c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66a5c-116">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="66a5c-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="66a5c-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66a5c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a5c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66a5c-118">See also</span></span>
- [<span data-ttu-id="66a5c-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="66a5c-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
