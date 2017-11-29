---
title: Enumerazione CorDebugRecordFormat
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugRecordFormat
api_location: mscordbi.dll
api_type: COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c2f8397382dde061078a0d96114420f1c5f48669
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="c57a9-102">Enumerazione CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="c57a9-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="c57a9-103">Descrive il formato dei dati in una matrice di byte che contiene informazioni su un evento di debug per le eccezioni native.</span><span class="sxs-lookup"><span data-stu-id="c57a9-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c57a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c57a9-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="c57a9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c57a9-105">Members</span></span>  
  
|<span data-ttu-id="c57a9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c57a9-106">Member</span></span>|<span data-ttu-id="c57a9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c57a9-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="c57a9-108">I dati corrispondono a un record di eccezione Windows a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="c57a9-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="c57a9-109">I dati corrispondono a un record di eccezione Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="c57a9-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c57a9-110">Note</span><span class="sxs-lookup"><span data-stu-id="c57a9-110">Remarks</span></span>  
 <span data-ttu-id="c57a9-111">Un membro del `CorDebugRecordFormat` enumerazione viene passata al [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) metodo per indicare il formato della matrice di byte nel relativo `pRecord` argomento.</span><span class="sxs-lookup"><span data-stu-id="c57a9-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c57a9-112">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c57a9-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c57a9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c57a9-113">Requirements</span></span>  
 <span data-ttu-id="c57a9-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c57a9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c57a9-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c57a9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c57a9-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c57a9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c57a9-117">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c57a9-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c57a9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c57a9-118">See Also</span></span>  
 [<span data-ttu-id="c57a9-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="c57a9-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
