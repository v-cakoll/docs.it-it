---
title: Metodo ISymUnmanagedENCUpdate::GetLocalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: 5e5bf097a4b1e366fff807595b22c4696a91cf43
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614552"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a>Metodo ISymUnmanagedENCUpdate::GetLocalVariables
Ottiene le variabili locali.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a>Parametri  
 `mdMethodToken`  
 in Token di metadati del metodo.  
  
 `cLocals`  
 in Oggetto `ULONG` che indica la dimensione del `rgLocals` parametro.  
  
 `rgLocals`  
 out Matrice restituita delle istanze di [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) .  
  
 `pceltFetched`  
 out Puntatore a un oggetto `ULONG` che riceve le dimensioni del `rgLocals` buffer necessarie per contenere le variabili locali.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedENCUpdate](isymunmanagedencupdate-interface.md)
