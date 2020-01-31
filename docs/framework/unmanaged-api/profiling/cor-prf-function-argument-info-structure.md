---
title: Struttura COR_PRF_FUNCTION_ARGUMENT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: c92ee580caed9f1fb87a31b676747769ad31a0e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867252"
---
# <a name="cor_prf_function_argument_info-structure"></a>Struttura COR_PRF_FUNCTION_ARGUMENT_INFO
Rappresenta gli argomenti di una funzione, in ordine da sinistra a destra.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`numRanges`|Numero di blocchi di argomenti. Questo valore corrisponde al numero di strutture [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) nella matrice di `ranges`.|  
|`totalArgumentSize`|Dimensione totale di tutti gli argomenti. In altre parole, questo valore è la somma delle lunghezze degli argomenti.|  
|`ranges`|Matrice di strutture di `COR_PRF_FUNCTION_ARGUMENT_RANGE`, ciascuna delle quali rappresenta un blocco di argomenti della funzione.|  
  
## <a name="remarks"></a>Note  
 Una funzione può avere molti argomenti. Tali argomenti potrebbero non essere archiviati in modo contiguo nella memoria. Si potrebbe avere un blocco di tre argomenti in un'unica posizione, un blocco di due argomenti in un'altra posizione e un blocco finale di un argomento in una posizione diversa. Questi argomenti sono tutti per la stessa funzione. sono archiviati solo in posizioni diverse.  
  
 La struttura `COR_PRF_FUNCTION_ARGUMENT_INFO` rappresenta tutti gli argomenti di una singola funzione. Usa una matrice per fare riferimento a tutti i blocchi degli argomenti della funzione. Per una singola funzione, quindi, è disponibile un'unica struttura di `COR_PRF_FUNCTION_ARGUMENT_INFO`, che fa riferimento a più strutture `COR_PRF_FUNCTION_ARGUMENT_RANGE`, ognuna delle quali punta a uno o più argomenti della funzione.  
  
 Gli argomenti archiviati nei registri vengono distribuiti in memoria per compilare le strutture.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di profilatura](profiling-structures.md)
