---
title: Metodo ICorDebugAppDomain::IsAttached
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0412089fee27e556c2f9230e9b34de3391b9bd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402561"
---
# <a name="icordebugappdomainisattached-method"></a>Metodo ICorDebugAppDomain::IsAttached
Ottiene un valore che indica se il debugger è collegato al dominio applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pbAttached`  
 [out] `true` se il debugger è collegato al dominio di applicazione; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Impossibile utilizzare i metodi dell'interfaccia ICorDebugController fino a quando il debugger viene connesso al dominio applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
