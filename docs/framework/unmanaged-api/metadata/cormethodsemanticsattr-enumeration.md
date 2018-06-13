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
ms.openlocfilehash: de467c98dfa7ad3eac69502f2afe311b301e1ec5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444809"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="c282e-102">Enumerazione CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="c282e-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="c282e-103">Contiene valori che descrivono la relazione tra un metodo e una proprietà o evento associato.</span><span class="sxs-lookup"><span data-stu-id="c282e-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c282e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c282e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c282e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c282e-105">Members</span></span>  
  
|<span data-ttu-id="c282e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c282e-106">Member</span></span>|<span data-ttu-id="c282e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c282e-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="c282e-108">Specifica che il metodo è un `set` funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="c282e-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="c282e-109">Specifica che il metodo è un `get` funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="c282e-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="c282e-110">Specifica che il metodo ha una relazione a una proprietà o un evento diversi da quelli definiti qui.</span><span class="sxs-lookup"><span data-stu-id="c282e-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="c282e-111">Specifica che il metodo aggiunge i metodi del gestore per un evento.</span><span class="sxs-lookup"><span data-stu-id="c282e-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="c282e-112">Specifica il metodo che rimuove i metodi del gestore per un evento.</span><span class="sxs-lookup"><span data-stu-id="c282e-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="c282e-113">Specifica che il metodo genera un evento.</span><span class="sxs-lookup"><span data-stu-id="c282e-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c282e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c282e-114">Requirements</span></span>  
 <span data-ttu-id="c282e-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c282e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c282e-116">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="c282e-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c282e-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c282e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c282e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c282e-118">See Also</span></span>  
 [<span data-ttu-id="c282e-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="c282e-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
