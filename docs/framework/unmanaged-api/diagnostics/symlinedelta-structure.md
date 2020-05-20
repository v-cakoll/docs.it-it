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
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609300"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="98308-102">Struttura SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="98308-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="98308-103">Fornisce informazioni al gestore di simboli sui metodi spostati in seguito a modifiche.</span><span class="sxs-lookup"><span data-stu-id="98308-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98308-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98308-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="98308-105">Membri</span><span class="sxs-lookup"><span data-stu-id="98308-105">Members</span></span>  
  
|<span data-ttu-id="98308-106">Membro</span><span class="sxs-lookup"><span data-stu-id="98308-106">Member</span></span>|<span data-ttu-id="98308-107">Description</span><span class="sxs-lookup"><span data-stu-id="98308-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="98308-108">Token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="98308-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="98308-109">Il numero di righe in cui è stato spostato il metodo.</span><span class="sxs-lookup"><span data-stu-id="98308-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98308-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98308-110">Requirements</span></span>  
 <span data-ttu-id="98308-111">**Intestazione:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="98308-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98308-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98308-112">See also</span></span>

- [<span data-ttu-id="98308-113">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="98308-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
