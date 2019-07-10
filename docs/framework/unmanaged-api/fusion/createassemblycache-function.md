---
title: Funzione CreateAssemblyCache
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffeb04ddcec290f899556bf0d8078acfb06707ac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778599"
---
# <a name="createassemblycache-function"></a>Funzione CreateAssemblyCache
Ottiene un puntatore a una nuova [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) istanza che rappresenta la global assembly cache.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `ppAsmCache`  
 [out] L'oggetto restituito `IAssemblyCache` puntatore.  
  
 `dwReserved`  
 [in] Riservato per un'estendibilità futura. `dwReserved` deve essere 0 (zero).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [Global Assembly Cache](../../../../docs/framework/app-domains/gac.md)
