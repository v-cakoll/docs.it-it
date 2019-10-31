---
title: Metodo IAssemblyEnum::GetNextAssembly
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
ms.openlocfilehash: ade404557d65fa073b6a0e66fe8234b41223ecde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134441"
---
# <a name="iassemblyenumgetnextassembly-method"></a>Metodo IAssemblyEnum::GetNextAssembly
Ottiene un puntatore al [IAssemblyName](iassemblyname-interface.md) successivo contenuto nell'oggetto [IAssemblyEnum](iassemblyenum-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pvReserved`  
 in Riservato per l'estendibilità futura. `pvReserved` deve essere un riferimento null.  
  
 `ppName`  
 out Puntatore `IAssemblyName` restituito.  
  
 `dwFlags`  
 in Riservato per l'estendibilità futura. `dwFlags` deve essere 0 (zero).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyName](iassemblyname-interface.md)
- [Interfaccia IAssemblyEnum](iassemblyenum-interface.md)
