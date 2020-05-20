---
title: Metodo ISymUnmanagedNamespace::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: 091f497024b48589953456e1ea6daf6635738240
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615085"
---
# <a name="isymunmanagednamespacegetvariables-method"></a>Metodo ISymUnmanagedNamespace::GetVariables
Restituisce tutte le variabili definite in ambito globale all'interno di questo spazio dei nomi.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `cVars`  
 in Oggetto `ULONG32` che indica la dimensione della `pVars` matrice.  
  
 `pcVars`  
 out Puntatore a un oggetto `ULONG32` che riceve la dimensione del buffer necessario per contenere gli spazi dei nomi.  
  
 `pVars`  
 out Puntatore a un buffer che contiene gli spazi dei nomi.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedNamespace](isymunmanagednamespace-interface.md)
