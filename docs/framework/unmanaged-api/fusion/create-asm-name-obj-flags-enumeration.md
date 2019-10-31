---
title: Enumerazione CREATE_ASM_NAME_OBJ_FLAGS
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
ms.openlocfilehash: f6abb59c3aaec40a4e7b228b8c69147a2d454431
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108873"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="5f4c0-102">Enumerazione CREATE_ASM_NAME_OBJ_FLAGS</span><span class="sxs-lookup"><span data-stu-id="5f4c0-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="5f4c0-103">Specifica gli attributi di un oggetto [interfaccia IAssemblyName](iassemblyname-interface.md) quando viene creato dalla funzione [CreateAssemblyNameObject](createassemblynameobject-function.md) .</span><span class="sxs-lookup"><span data-stu-id="5f4c0-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f4c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f4c0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="5f4c0-105">Members</span><span class="sxs-lookup"><span data-stu-id="5f4c0-105">Members</span></span>  
  
|<span data-ttu-id="5f4c0-106">Member</span><span class="sxs-lookup"><span data-stu-id="5f4c0-106">Member</span></span>|<span data-ttu-id="5f4c0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f4c0-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="5f4c0-108">Indica che il parametro passato è un'identità testuale.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="5f4c0-109">Imposta alcuni valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="5f4c0-110">Verifica la regola di assembly Friend (solo nome e chiave pubblica).</span><span class="sxs-lookup"><span data-stu-id="5f4c0-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="5f4c0-111">Questo membro è solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="5f4c0-112">Combinazione dei flag di `CANOF_PARSE_DISPLAY_NAME` e di `CANOF_VERIFY_FRIEND_ASSEMBLYNAME`.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="5f4c0-113">Questo membro è solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f4c0-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f4c0-114">Requirements</span></span>  
 <span data-ttu-id="5f4c0-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f4c0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f4c0-116">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5f4c0-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5f4c0-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f4c0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f4c0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f4c0-118">See also</span></span>

- [<span data-ttu-id="5f4c0-119">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="5f4c0-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="5f4c0-120">Funzione CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="5f4c0-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="5f4c0-121">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="5f4c0-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
