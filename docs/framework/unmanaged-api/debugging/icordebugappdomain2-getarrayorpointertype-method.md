---
title: Metodo ICorDebugAppDomain2::GetArrayOrPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3f0ca6d930b22f30fe9bbc5b5a04bf1e034f34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405825"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>Metodo ICorDebugAppDomain2::GetArrayOrPointerType
Ottiene una matrice di tipo specificato, o un puntatore o un riferimento al tipo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `elementType`  
 [in] Valore dell'enumerazione CorElementType che specifica il tipo nativo sottostante (una matrice, un puntatore o riferimento) da creare.  
  
 `nRank`  
 [in] La classificazione (numero di dimensioni) della matrice. Questo valore deve essere 0 se `elementType` specifica un tipo puntatore o riferimento.  
  
 `pTypeArg`  
 [in] Un puntatore a un oggetto ICorDebugType che rappresenta il tipo di matrice, puntatore o riferimento da creare.  
  
 `ppType`  
 [out] Un puntatore all'indirizzo di un `ICorDebugType` tipo di oggetto che rappresenta la matrice costruito, il tipo di puntatore o riferimento.  
  
## <a name="remarks"></a>Note  
 Il valore di *elementType* deve essere uno dei seguenti:  
  
-   ELEMENT_TYPE_PTR  
  
-   ELEMENT_TYPE_BYREF  
  
-   ELEMENT_TYPE_ARRAY o ELEMENT_TYPE_SZARRAY  
  
 Se il valore di *elementType* è ELEMENT_TYPE_PTR o ELEMENT_TYPE_BYREF, *nDimensioni* deve essere zero.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
