---
title: Struttura BucketParameters
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf52f74c38b479664ad7e015180b26e0a53c235e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508301"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="be937-102">Struttura BucketParameters</span><span class="sxs-lookup"><span data-stu-id="be937-102">BucketParameters Structure</span></span>
<span data-ttu-id="be937-103">Archivia il nome del tipo di un evento e i parametri per l'eccezione corrente viene associato all'evento.</span><span class="sxs-lookup"><span data-stu-id="be937-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be937-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be937-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="be937-105">Membri</span><span class="sxs-lookup"><span data-stu-id="be937-105">Members</span></span>  
  
|<span data-ttu-id="be937-106">Membro</span><span class="sxs-lookup"><span data-stu-id="be937-106">Member</span></span>|<span data-ttu-id="be937-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be937-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="be937-108">`true`, se il resto di questa struttura è valido. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="be937-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="be937-109">Nome del tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="be937-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="be937-110">Matrice di stringhe, ognuna delle quali specifica un parametro per l'eccezione corrente associato all'evento.</span><span class="sxs-lookup"><span data-stu-id="be937-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be937-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be937-111">Requirements</span></span>  
 <span data-ttu-id="be937-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be937-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be937-113">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="be937-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="be937-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be937-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be937-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be937-115">See also</span></span>
- [<span data-ttu-id="be937-116">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="be937-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
