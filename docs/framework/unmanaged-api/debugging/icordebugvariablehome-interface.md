---
title: Interfaccia ICorDebugVariableHome
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
ms.openlocfilehash: caf6a24207be98be9afb10be2bd027b51405fa3b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396543"
---
# <a name="icordebugvariablehome-interface"></a>Interfaccia ICorDebugVariableHome
Rappresenta una variabile locale o un argomento di una funzione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetArgumentIndex](icordebugvariablehome-getargumentindex-method.md)|Ottiene l'indice di un argomento della funzione.|  
|[Metodo GetCode](icordebugvariablehome-getcode-method.md)|Ottiene l'istanza "ICorDebugCode" che contiene questo `ICorDebugVariableHome` oggetto.|  
|[Metodo GetLiveRange](icordebugvariablehome-getliverange-method.md)|Ottiene l'intervallo nativo su cui questa variabile è attiva.|  
|[Metodo GetLocationType](icordebugvariablehome-getlocationtype-method.md)|Ottiene il tipo della posizione nativa della variabile.|  
|[Metodo GetOffset](icordebugvariablehome-getoffset-method.md)|Ottiene l'offset dal registro di base per una variabile.|  
|[Metodo GetRegister](icordebugvariablehome-getregister-method.md)|Ottiene il registro contenente una variabile con un tipo di posizione `VLT_REGISTER` e il registro di base per una variabile con un tipo di posizione `VLT_REGISTER_RELATIVE` .|  
|[Metodo GetSlotIndex](icordebugvariablehome-getslotindex-method.md)|Ottiene l'indice di slot gestito di una variabile locale.|  
  
## <a name="example"></a>Esempio  
 Nel frammento di codice seguente viene utilizzato l'oggetto [interfacce icordebugcode4](icordebugcode4-interface.md) denominato `pCode4` .  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)
- [Interfaccia ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)
