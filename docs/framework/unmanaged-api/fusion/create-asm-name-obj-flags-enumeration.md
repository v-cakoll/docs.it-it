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
# <a name="create_asm_name_obj_flags-enumeration"></a>Enumerazione CREATE_ASM_NAME_OBJ_FLAGS
Specifica gli attributi di un oggetto [interfaccia IAssemblyName](iassemblyname-interface.md) quando viene creato dalla funzione [CreateAssemblyNameObject](createassemblynameobject-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|Indica che il parametro passato è un'identità testuale.|  
|`CANOF_SET_DEFAULT_VALUES`|Imposta alcuni valori predefiniti.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Verifica la regola di assembly Friend (solo nome e chiave pubblica). Questo membro è solo per uso interno.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Combinazione dei flag di `CANOF_PARSE_DISPLAY_NAME` e di `CANOF_VERIFY_FRIEND_ASSEMBLYNAME`. Questo membro è solo per uso interno.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyName](iassemblyname-interface.md)
- [Funzione CreateAssemblyNameObject](createassemblynameobject-function.md)
- [Enumerazioni Fusion](fusion-enumerations.md)
