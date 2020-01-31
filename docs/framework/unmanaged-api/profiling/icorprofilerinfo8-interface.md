---
title: Interfaccia ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 476bcbd91188e3ff9eb63f50cfa2118a440b1a69
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868317"
---
# <a name="icorprofilerinfo8-interface"></a>Interfaccia ICorProfilerInfo8

Sottoclasse di [ICorProfilerInfo7](icorprofilerinfo7-interface.md) che fornisce metodi per eseguire query sulle informazioni sui metodi dinamici.

## <a name="methods"></a>Metodi  

| Metodo|Descrizione|  
| ------------|-----------------|  
|[Metodo IsFunctionDynamic](icorprofilerinfo8-isfunctiondynamic-method.md)| Determina se una funzione non dispone di metadati associati.|
|[Metodo GetFunctionFromIP3](icorprofilerinfo8-getfunctionfromip3-method.md)| Esegue il mapping di un puntatore all'istruzione di codice gestito a un FunctionID. Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici. |
|[Metodo GetDynamicFunctionInfo](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| Recupera informazioni sui metodi dinamici. |

## <a name="requirements"></a>Requisiti di  
**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** CorProf.idl, CorProf.h  
**Versioni .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
