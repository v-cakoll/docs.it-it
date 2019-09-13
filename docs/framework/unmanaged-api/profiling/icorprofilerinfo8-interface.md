---
title: Interfaccia ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2baa33a7a3527392d8095b5d0ec7ad6af8a71a8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928929"
---
# <a name="icorprofilerinfo8-interface"></a>Interfaccia ICorProfilerInfo8

Sottoclasse di [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) che fornisce metodi per eseguire query sulle informazioni sui metodi dinamici.

## <a name="methods"></a>Metodi  

| Metodo|DESCRIZIONE|  
| ------------|-----------------|  
|[Metodo IsFunctionDynamic](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| Determina se una funzione non dispone di metadati associati.|
|[Metodo GetFunctionFromIP3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| Esegue il mapping di un puntatore all'istruzione di codice gestito a un FunctionID. Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici. |
|[Metodo GetDynamicFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| Recupera informazioni sui metodi dinamici. |

## <a name="requirements"></a>Requisiti  
**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** CorProf. idl, CorProf. h  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
