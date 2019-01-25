---
title: Funzione CreateAssemblyNameObject
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1412231b53763ce8e6c2400497396d2f178d8e7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666293"
---
# <a name="createassemblynameobject-function"></a>Funzione CreateAssemblyNameObject
Ottiene un puntatore a interfaccia a un [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) istanza che rappresenta l'identità univoca dell'assembly con il nome specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppAssemblyNameObj`  
 [out] L'oggetto restituito `IAssemblyName`.  
  
 `szAssemblyName`  
 [in] Il nome dell'assembly per cui si desidera creare il nuovo `IAssemblyName` istanza.  
  
 `dwFlags`  
 [in] Flag da passare al costruttore dell'oggetto.  
  
 `pvReserved`  
 [in] Riservato per un'estendibilità futura. `pvReserved` deve essere un riferimento null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
