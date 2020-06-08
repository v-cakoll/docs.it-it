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
ms.openlocfilehash: 9fca75ae59b95a226b51768b3e1bfb220d9926f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500962"
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`numRanges`|Numero di blocchi di argomenti. Questo valore corrisponde al numero di strutture [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) nella `ranges` matrice.|  
|`totalArgumentSize`|Dimensione totale di tutti gli argomenti. In altre parole, questo valore è la somma delle lunghezze degli argomenti.|  
|`ranges`|Matrice di `COR_PRF_FUNCTION_ARGUMENT_RANGE` strutture, ognuna delle quali rappresenta un blocco di argomenti della funzione.|  
  
## <a name="remarks"></a>Osservazioni  
 Una funzione può avere molti argomenti. Tali argomenti potrebbero non essere archiviati in modo contiguo nella memoria. Si potrebbe avere un blocco di tre argomenti in un'unica posizione, un blocco di due argomenti in un'altra posizione e un blocco finale di un argomento in una posizione diversa. Questi argomenti sono tutti per la stessa funzione. sono archiviati solo in posizioni diverse.  
  
 La `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura rappresenta tutti gli argomenti di una singola funzione. Usa una matrice per fare riferimento a tutti i blocchi degli argomenti della funzione. Per una singola funzione, quindi, è presente una singola `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura, che fa riferimento `COR_PRF_FUNCTION_ARGUMENT_RANGE` a più strutture, ognuna delle quali punta a uno o più argomenti della funzione.  
  
 Gli argomenti archiviati nei registri vengono distribuiti in memoria per compilare le strutture.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di profilatura](profiling-structures.md)
