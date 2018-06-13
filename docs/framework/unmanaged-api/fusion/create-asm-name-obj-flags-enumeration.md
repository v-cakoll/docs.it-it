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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2997bb90f2d9034de398b901fcbd6265dcb59998
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430486"
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="fe0c8-102">Enumerazione CREATE_ASM_NAME_OBJ_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fe0c8-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="fe0c8-103">Specifica gli attributi di un [IAssemblyName (interfaccia)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) oggetto quando viene creato per il [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="fe0c8-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe0c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe0c8-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="fe0c8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="fe0c8-105">Members</span></span>  
  
|<span data-ttu-id="fe0c8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="fe0c8-106">Member</span></span>|<span data-ttu-id="fe0c8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe0c8-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="fe0c8-108">Indica che il parametro passato è un'identità testuale.</span><span class="sxs-lookup"><span data-stu-id="fe0c8-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="fe0c8-109">Imposta alcuni valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="fe0c8-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="fe0c8-110">Verifica la regola di assembly friend (solo nome e chiave pubblica).</span><span class="sxs-lookup"><span data-stu-id="fe0c8-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="fe0c8-111">Questo membro è solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="fe0c8-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="fe0c8-112">Una combinazione del `CANOF_PARSE_DISPLAY_NAME` e `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flag.</span><span class="sxs-lookup"><span data-stu-id="fe0c8-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="fe0c8-113">Questo membro è solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="fe0c8-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe0c8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe0c8-114">Requirements</span></span>  
 <span data-ttu-id="fe0c8-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe0c8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe0c8-116">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fe0c8-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fe0c8-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe0c8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe0c8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe0c8-118">See Also</span></span>  
 [<span data-ttu-id="fe0c8-119">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="fe0c8-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="fe0c8-120">Funzione CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="fe0c8-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 [<span data-ttu-id="fe0c8-121">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="fe0c8-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
