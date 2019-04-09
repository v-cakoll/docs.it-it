---
title: Enumerazione CorDebugRecordFormat
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: add1458bb3a50a5e5433e8cc7baaf47d750c927d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083673"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="2f40a-102">Enumerazione CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="2f40a-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="2f40a-103">Descrive il formato dei dati in una matrice di byte che contiene informazioni su un evento di debug per le eccezioni native.</span><span class="sxs-lookup"><span data-stu-id="2f40a-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f40a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f40a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="2f40a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2f40a-105">Members</span></span>  
  
|<span data-ttu-id="2f40a-106">Member</span><span class="sxs-lookup"><span data-stu-id="2f40a-106">Member</span></span>|<span data-ttu-id="2f40a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f40a-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="2f40a-108">I dati corrispondono a un record di eccezione Windows a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="2f40a-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="2f40a-109">I dati corrispondono a un record di eccezione Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="2f40a-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f40a-110">Note</span><span class="sxs-lookup"><span data-stu-id="2f40a-110">Remarks</span></span>  
 <span data-ttu-id="2f40a-111">Un membro del `CorDebugRecordFormat` enumerazione viene passata al [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) metodo per indicare il formato della matrice di byte nella relativa `pRecord` argomento.</span><span class="sxs-lookup"><span data-stu-id="2f40a-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f40a-112">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2f40a-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f40a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f40a-113">Requirements</span></span>  
 <span data-ttu-id="2f40a-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f40a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f40a-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f40a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f40a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f40a-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2f40a-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2f40a-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f40a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f40a-118">See also</span></span>

- [<span data-ttu-id="2f40a-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="2f40a-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
