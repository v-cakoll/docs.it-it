---
title: Metodo IDebugAutoAttach::AutoAttach
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
ms.openlocfilehash: aae03b0dc76639c50f4615d41eef73990226b5f7
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442124"
---
# <a name="idebugautoattachautoattach-method"></a>Metodo IDebugAutoAttach::AutoAttach
Esegue la connessione automatica al debugger richiamato dal server.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `guidPort`  
 in Sempre impostato su `GUID_NULL` .  
  
 `dwPid`  
 in ID processo, normalmente recuperato con la `GetCurrentProcessId` funzione.  
  
 `dwProgramType`  
 in Tipo di programma: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` o `AUTOATTACH_PROGRAM_UNKNOWN` .  
  
 `dwProgramId`  
 in ID programma.  
  
 `pszSessionId`  
 in Stringa passata dal verbo di debug.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** DbgAutoAttach. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IDebugAutoAttach](idebugautoattach-interface.md)
