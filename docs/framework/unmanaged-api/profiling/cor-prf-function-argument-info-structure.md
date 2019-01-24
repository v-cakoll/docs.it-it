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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bb92f9ba8ff0aed1c6eb1fa44fb4d7c9abc186a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714231"
---
# <a name="corprffunctionargumentinfo-structure"></a>Struttura COR_PRF_FUNCTION_ARGUMENT_INFO
Rappresenta gli argomenti di una funzione, in ordine da sinistra a destra.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`numRanges`|Il numero di blocchi di argomenti. Vale a dire, questo valore è il numero di [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) le strutture nel `ranges` matrice.|  
|`totalArgumentSize`|Le dimensioni totali di tutti gli argomenti. In altre parole, questo valore è la somma delle lunghezze degli argomenti.|  
|`ranges`|Matrice di `COR_PRF_FUNCTION_ARGUMENT_RANGE` strutture, ognuno dei quali rappresenta un blocco di argomenti della funzione.|  
  
## <a name="remarks"></a>Note  
 Una funzione può avere un numero di argomenti. Tali argomenti non possono essere archiviati in modo contiguo nella memoria. Potrebbe essere un blocco di tre argomenti in un'unica posizione, un blocco di due argomenti in un'altra posizione e un blocco finale di un argomento in una posizione diversa. Questi argomenti sono tutti della stessa funzione; sono semplicemente archiviati in posizioni diverse.  
  
 Il `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura rappresenta tutti gli argomenti di una singola funzione. Usa una matrice per fare riferimento a tutti i blocchi degli argomenti della funzione. Per una singola funzione, non sarà pertanto necessario un unico `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura, a cui fa riferimento a più `COR_PRF_FUNCTION_ARGUMENT_RANGE` strutture, ognuno dei quali punta a uno o più argomenti di funzione.  
  
 Gli argomenti che vengono archiviati nei registri sono stati distribuiti in memoria per compilare le strutture.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Strutture di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
