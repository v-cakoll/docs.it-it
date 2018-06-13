---
title: Struttura SYMLINEDELTA
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77cd8b7d791d11f6d40386f4747c60cd4832521a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428094"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="df4c9-102">Struttura SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="df4c9-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="df4c9-103">Fornisce informazioni per il gestore dei simboli sui metodi che sono stati spostati in seguito a modifiche.</span><span class="sxs-lookup"><span data-stu-id="df4c9-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df4c9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df4c9-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="df4c9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="df4c9-105">Members</span></span>  
  
|<span data-ttu-id="df4c9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="df4c9-106">Member</span></span>|<span data-ttu-id="df4c9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df4c9-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="df4c9-108">Token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="df4c9-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="df4c9-109">Il numero di righe, che il metodo è stato spostato.</span><span class="sxs-lookup"><span data-stu-id="df4c9-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df4c9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df4c9-110">Requirements</span></span>  
 <span data-ttu-id="df4c9-111">**Intestazione:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="df4c9-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df4c9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df4c9-112">See Also</span></span>  
 [<span data-ttu-id="df4c9-113">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="df4c9-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
