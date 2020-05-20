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
ms.openlocfilehash: 7037065be138c369b847e7f86de7b46fc5ae601a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616879"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="1ff9e-102">Struttura BucketParameters</span><span class="sxs-lookup"><span data-stu-id="1ff9e-102">BucketParameters Structure</span></span>
<span data-ttu-id="1ff9e-103">Archivia il nome del tipo di un evento e i parametri per l'eccezione corrente associata all'evento.</span><span class="sxs-lookup"><span data-stu-id="1ff9e-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ff9e-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="1ff9e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1ff9e-105">Members</span></span>  
  
|<span data-ttu-id="1ff9e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1ff9e-106">Member</span></span>|<span data-ttu-id="1ff9e-107">Description</span><span class="sxs-lookup"><span data-stu-id="1ff9e-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="1ff9e-108">`true`Se il resto della struttura è valido; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="1ff9e-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="1ff9e-109">Nome del tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="1ff9e-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="1ff9e-110">Matrice di stringhe, ognuna delle quali specifica un parametro per l'eccezione corrente associata all'evento.</span><span class="sxs-lookup"><span data-stu-id="1ff9e-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ff9e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1ff9e-111">Requirements</span></span>  
 <span data-ttu-id="1ff9e-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ff9e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ff9e-113">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="1ff9e-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1ff9e-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ff9e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff9e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ff9e-115">See also</span></span>

- [<span data-ttu-id="1ff9e-116">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="1ff9e-116">Hosting Structures</span></span>](hosting-structures.md)
