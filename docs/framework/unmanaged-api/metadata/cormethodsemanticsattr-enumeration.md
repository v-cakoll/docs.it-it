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
ms.openlocfilehash: 4b09ccfdb33c9853ed97005461f2288f1e7e6fd1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781743"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="47c44-102">Enumerazione CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="47c44-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="47c44-103">Contiene valori che descrivono la relazione tra un metodo e una proprietà o evento associato.</span><span class="sxs-lookup"><span data-stu-id="47c44-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47c44-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="47c44-105">Membri</span><span class="sxs-lookup"><span data-stu-id="47c44-105">Members</span></span>  
  
|<span data-ttu-id="47c44-106">Member</span><span class="sxs-lookup"><span data-stu-id="47c44-106">Member</span></span>|<span data-ttu-id="47c44-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47c44-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="47c44-108">Specifica che il metodo è un `set` della funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="47c44-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="47c44-109">Specifica che il metodo è un `get` della funzione di accesso per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="47c44-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="47c44-110">Specifica che il metodo ha una relazione a una proprietà o un evento diverso da quelli definiti qui.</span><span class="sxs-lookup"><span data-stu-id="47c44-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="47c44-111">Specifica che il metodo aggiunge i metodi del gestore per un evento.</span><span class="sxs-lookup"><span data-stu-id="47c44-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="47c44-112">Specifica il metodo che rimuove i metodi gestore per un evento.</span><span class="sxs-lookup"><span data-stu-id="47c44-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="47c44-113">Specifica che il metodo genera un evento.</span><span class="sxs-lookup"><span data-stu-id="47c44-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47c44-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47c44-114">Requirements</span></span>  
 <span data-ttu-id="47c44-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47c44-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47c44-116">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="47c44-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="47c44-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47c44-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c44-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47c44-118">See also</span></span>

- [<span data-ttu-id="47c44-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="47c44-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
