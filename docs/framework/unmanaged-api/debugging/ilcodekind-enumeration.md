---
title: Enumerazione ILCodeKind
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
ms.openlocfilehash: 20e2e3f177b12221832786f4fab86635098d1989
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790495"
---
# <a name="ilcodekind-enumeration"></a>Enumerazione ILCodeKind
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Fornisce valori che specificano se il debugger può accedere a variabili locali o a codice aggiunto nella strumentazione ReJIT del profiler.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a>Membri  
  
|Nome membro|Descrizione|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|Il debugger non ha accesso alle informazioni della strumentazione ReJIT.|  
|`ILCODE_REJIT_IL`|Il debugger ha accesso alle informazioni della strumentazione ReJIT.|  
  
## <a name="remarks"></a>Note  
 Un membro dell'enumerazione `ILCodeKind` può essere passato ai metodi [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) e [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) per determinare se il debugger può accedere a variabili aggiunte nella strumentazione ReJIT del profiler e al metodo [GetCodeEx](icordebugilframe4-getcodeex-method.md) per determinare se IL debugger può accedere al linguaggio il instrumentato.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Interfaccia ICorDebugILFrame4](icordebugilframe4-interface.md)
- [ReJIT: Guida alle procedure](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
