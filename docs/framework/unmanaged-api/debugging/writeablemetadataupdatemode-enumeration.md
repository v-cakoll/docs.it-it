---
title: Enumerazione WriteableMetadataUpdateMode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
ms.openlocfilehash: 5c3f2f7a9c0804b71c9c8a52bb032aca7c03825e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790297"
---
# <a name="writeablemetadataupdatemode-enumeration"></a><span data-ttu-id="6ec64-102">Enumerazione WriteableMetadataUpdateMode</span><span class="sxs-lookup"><span data-stu-id="6ec64-102">WriteableMetadataUpdateMode Enumeration</span></span>
<span data-ttu-id="6ec64-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="6ec64-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6ec64-104">Fornisce i valori che specificano se gli aggiornamenti in memoria ai metadati sono visibili a un debugger.</span><span class="sxs-lookup"><span data-stu-id="6ec64-104">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec64-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ec64-105">Syntax</span></span>  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a><span data-ttu-id="6ec64-106">Membri</span><span class="sxs-lookup"><span data-stu-id="6ec64-106">Members</span></span>  
  
|<span data-ttu-id="6ec64-107">Nome membro</span><span class="sxs-lookup"><span data-stu-id="6ec64-107">Member name</span></span>|<span data-ttu-id="6ec64-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ec64-108">Description</span></span>|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|<span data-ttu-id="6ec64-109">Mantiene la compatibilità con le versioni precedenti di .NET Framework quando vengono resi visibili gli aggiornamenti in memoria ai metadati.</span><span class="sxs-lookup"><span data-stu-id="6ec64-109">Maintain compatibility with previous versions of the .NET Framework when making in-memory updates to metadata visible.</span></span> <span data-ttu-id="6ec64-110">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="6ec64-110">See the Remarks section for more information.</span></span>|  
|`AlwaysShowUpdates`|<span data-ttu-id="6ec64-111">Rende visibili al debugger gli aggiornamenti in memoria ai metadati.</span><span class="sxs-lookup"><span data-stu-id="6ec64-111">Make in-memory updates to metadata visible to the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ec64-112">Note</span><span class="sxs-lookup"><span data-stu-id="6ec64-112">Remarks</span></span>  
 <span data-ttu-id="6ec64-113">Un membro dell'enumerazione `WriteableMetadataUpdateMode` può essere passato al metodo [SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md) per controllare se gli aggiornamenti in memoria ai metadati nel processo di destinazione sono visibili al debugger.</span><span class="sxs-lookup"><span data-stu-id="6ec64-113">A member of the `WriteableMetadataUpdateMode` enumeration can be passed to the [SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md) method to control whether in-memory updates to metadata in the target process are visible to the debugger.</span></span>  
  
 <span data-ttu-id="6ec64-114">L'opzione `LegacyCompatPolicy` applica lo stesso comportamento delle versioni di .NET Framework precedenti alla 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="6ec64-114">The `LegacyCompatPolicy` option enforces the same behavior as in versions of the .NET Framework before 4.5.2.</span></span> <span data-ttu-id="6ec64-115">Spesso questo significa che i metadati degli aggiornamenti non sono visibili.</span><span class="sxs-lookup"><span data-stu-id="6ec64-115">This often means that metadata from updates is not visible.</span></span> <span data-ttu-id="6ec64-116">Tuttavia, le chiamate a una serie di metodi di debug forzano in modo implicito il debugger a rendere visibili gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="6ec64-116">However, calls to a number of debugging methods implicitly coerce the debugger to make updates visible.</span></span> <span data-ttu-id="6ec64-117">Se, ad esempio, il debugger passa [ICorDebugILFrame:: GetLocalVariable](icordebugilframe-getlocalvariable-method.md) , l'indice di una variabile non è stato trovato nei metadati originali del metodo, tutti i metadati per il modulo vengono aggiornati a uno snapshot corrispondente allo stato corrente del processo.</span><span class="sxs-lookup"><span data-stu-id="6ec64-117">For example, if the debugger passes [ICorDebugILFrame::GetLocalVariable](icordebugilframe-getlocalvariable-method.md) the index of a variable not found in the method's original metadata, all metadata for the module is updated to a snapshot matching the current state of the process.</span></span> <span data-ttu-id="6ec64-118">In altre parole, con l'opzione `LegacyCompatPolicy` il debugger potrebbe visualizzare tutti gli aggiornamenti dei metadati disponibili, solo alcuni o nessuno, a seconda di come usa le altre parti dell'API di debug non gestito.</span><span class="sxs-lookup"><span data-stu-id="6ec64-118">In other words, with the `LegacyCompatPolicy` option, the debugger might see none, some, or all of the available metadata updates, depending on how it uses other parts of the unmanaged debugging API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ec64-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="6ec64-119">Requirements</span></span>  
 <span data-ttu-id="6ec64-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ec64-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ec64-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ec64-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ec64-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ec64-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ec64-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ec64-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec64-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ec64-124">See also</span></span>

- [<span data-ttu-id="6ec64-125">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="6ec64-125">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="6ec64-126">Metodo SetWriteableMetadataUpdateMode</span><span class="sxs-lookup"><span data-stu-id="6ec64-126">SetWriteableMetadataUpdateMode Method</span></span>](icordebugprocess7-setwriteablemetadataupdatemode-method.md)
