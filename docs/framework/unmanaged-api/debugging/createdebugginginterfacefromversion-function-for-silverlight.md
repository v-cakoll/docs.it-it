---
title: Funzione di Silverlight CreateDebuggingInterfaceFromVersion
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: c83bdcca4fab75b4ae94500ceb785b6000cd802a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860873"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a>Funzione di Silverlight CreateDebuggingInterfaceFromVersion
Accetta una stringa di versione Common Language Runtime (CLR) restituita dalla [funzione CreateVersionStringFromModule](createversionstringfrommodule-function.md)e restituisce un'interfaccia del debugger corrispondente (in genere, [ICorDebug](icordebug-interface.md)).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szDebuggeeVersion`  
 in Stringa di versione di CLR nell'oggetto del debug di destinazione, restituito dalla [funzione CreateVersionStringFromModule](createversionstringfrommodule-function.md).  
  
 `ppCordb`  
 [out] Puntatore a un puntatore a un oggetto COM (`IUnknown`). Viene eseguito il cast di questo oggetto a un oggetto [ICorDebug](icordebug-interface.md) prima che venga restituito.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 `ppCordb`fa riferimento a un oggetto valido che implementa l'interfaccia dell' [interfaccia ICorDebug](icordebug-interface.md) .  
  
 E_INVALIDARG  
 `szDebuggeeVersion` o `ppCordb` è null.  
  
 CORDBG_E_DEBUG_COMPONENT_MISSING  
 Impossibile trovare un componente necessario per il debug CLR. Ciò significa che non è stato possibile trovare mscordaccore.dll o mscordbi.dll nella stessa directory del file CoreCLR.dll di destinazione.  
  
 CORDBG_E_INCOMPATIBLE_PROTOCOL  
 Significa che la versione di mscordaccore.dll o mscordbi.dll non corrisponde a quella del file CoreCLR.dll di destinazione.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Impossibile restituire un' [interfaccia ICorDebug](icordebug-interface.md).  
  
## <a name="remarks"></a>Osservazioni  
 L'interfaccia restituita fornisce funzionalità per connettersi a un CLR nel processo di destinazione ed eseguire il debug del codice gestito eseguito da CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** dbgshim. h  
  
 **Libreria:** dbgshim. dll  
  
 **Versioni .NET Framework:** 3,5 SP1
