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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5064e66708044d82e3a097c8235b5b28a3412200
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077134"
---
# <a name="idebugautoattachautoattach-method"></a>Metodo IDebugAutoAttach::AutoAttach
Esegue automaticamente richiamato server debugger collegare.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in] Sempre impostato su `GUID_NULL`.  
  
 `dwPid`  
 [in] ID processo, in genere recuperato con il `GetCurrentProcessId` (funzione).  
  
 `dwProgramType`  
 [in] Tipo di programma: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, o `AUTOATTACH_PROGRAM_UNKNOWN`.  
  
 `dwProgramId`  
 [in] ID programma.  
  
 `pszSessionId`  
 [in] Stringa passata per il verbo debug.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** DbgAutoAttach.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IDebugAutoAttach](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
