---
title: Enumerazione ESymbolReadingPolicy
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 5c3d1d0ebc56ee93c950afb4f015c8e10ec6a0f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616177"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="8e9b7-102">Enumerazione ESymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="8e9b7-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="8e9b7-103">Contiene valori che impostano i criteri per la lettura dei file di database di programma (PDB).</span><span class="sxs-lookup"><span data-stu-id="8e9b7-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e9b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e9b7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="8e9b7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8e9b7-105">Members</span></span>  
  
|<span data-ttu-id="8e9b7-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8e9b7-106">Member</span></span>|<span data-ttu-id="8e9b7-107">Description</span><span class="sxs-lookup"><span data-stu-id="8e9b7-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="8e9b7-108">Specifica che il debugger deve sempre leggere i file PDB.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="8e9b7-109">Specifica che il debugger deve leggere solo i file PDB associati a assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="8e9b7-110">Specifica che il debugger non deve mai leggere i file PDB.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e9b7-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8e9b7-111">Remarks</span></span>  
 <span data-ttu-id="8e9b7-112">L' `ESymbolReadingPolicy` enumerazione viene utilizzata con il metodo [ICLRDebugManager:: SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8e9b7-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e9b7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e9b7-113">Requirements</span></span>  
 <span data-ttu-id="8e9b7-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e9b7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e9b7-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8e9b7-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e9b7-116">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8e9b7-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e9b7-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e9b7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9b7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e9b7-118">See also</span></span>

- [<span data-ttu-id="8e9b7-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="8e9b7-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
