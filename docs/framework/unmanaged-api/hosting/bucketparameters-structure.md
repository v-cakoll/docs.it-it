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
ms.openlocfilehash: 4d9de489bdeb0ab506f56ff08f4afb4cf6d0ab4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178284"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="5a55f-102">Struttura BucketParameters</span><span class="sxs-lookup"><span data-stu-id="5a55f-102">BucketParameters Structure</span></span>
<span data-ttu-id="5a55f-103">Archivia il nome del tipo di un evento e i parametri per l'eccezione corrente associata all'evento.</span><span class="sxs-lookup"><span data-stu-id="5a55f-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a55f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a55f-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="5a55f-105">Members</span><span class="sxs-lookup"><span data-stu-id="5a55f-105">Members</span></span>  
  
|<span data-ttu-id="5a55f-106">Membro</span><span class="sxs-lookup"><span data-stu-id="5a55f-106">Member</span></span>|<span data-ttu-id="5a55f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a55f-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="5a55f-108">`true`, se il resto di questa struttura è valido; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="5a55f-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="5a55f-109">Nome del tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="5a55f-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="5a55f-110">Matrice di stringhe, ognuna delle quali specifica un parametro per l'eccezione corrente associata all'evento.</span><span class="sxs-lookup"><span data-stu-id="5a55f-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a55f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a55f-111">Requirements</span></span>  
 <span data-ttu-id="5a55f-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a55f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a55f-113">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="5a55f-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5a55f-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a55f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a55f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a55f-115">See also</span></span>

- [<span data-ttu-id="5a55f-116">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="5a55f-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
