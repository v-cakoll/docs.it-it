---
title: Funzione CreateApplicationContext
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
ms.openlocfilehash: e188fe80e770481aac02244a2c105639e4da19e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108897"
---
# <a name="createapplicationcontext-function"></a>Funzione CreateApplicationContext
Questa funzione supporta l'infrastruttura .NET Framework e non può essere usata direttamente dal codice.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `pName`  
 in Puntatore a un nome descrittivo.  
  
 `ppCtx`  
 out Puntatore a un contesto dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Incluso come risorsa in Fusion. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyCache](iassemblycache-interface.md)
- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
- [Global Assembly Cache](../../app-domains/gac.md)
