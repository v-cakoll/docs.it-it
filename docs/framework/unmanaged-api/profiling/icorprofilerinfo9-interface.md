---
title: Interfaccia ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 431a546fb4a3b92b379e273553f0caf540ba1473
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449734"
---
# <a name="icorprofilerinfo9-interface"></a>Interfaccia ICorProfilerInfo9

Sottoclasse di [ICorProfilerInfo8](icorprofilerinfo8-interface.md) che fornisce metodi per eseguire query sulle informazioni sulle funzioni con più versioni di codice nativo.  

## <a name="methods"></a>Metodi  

| Metodo|Descrizione|  
| ------------|-----------------|  
|[Metodo GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md)| Dato un functionId e rejitId, enumera l'indirizzo iniziale del codice nativo di tutte le versioni compilato JIT del codice attualmente esistente. |
|[Metodo GetILToNativeMapping3](icorprofilerinfo9-getiltonativemapping3-method.md)| Dato l'indirizzo iniziale del codice nativo, restituisce le informazioni di mapping native a per la versione compilato JIT del codice. |
|[Metodo GetCodeInfo4](icorprofilerinfo9-getcodeinfo4-method.md)| Dato l'indirizzo iniziale del codice nativo, restituisce i blocchi di memoria virtuale che archiviano il codice. |

## <a name="requirements"></a>Requisiti  
**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).  
**Intestazione:** CorProf.idl, CorProf.h  
**Versioni di .NET:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
