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
ms.openlocfilehash: bbf43f3936823b9a8e562cb32cfa2eef08840033
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895183"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>Metodo ICorDebugAppDomain2::GetArrayOrPointerType
Ottiene una matrice del tipo specificato o un puntatore o un riferimento al tipo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `elementType`  
 in Valore dell'enumerazione CorElementType che specifica il tipo nativo sottostante, ovvero una matrice, un puntatore o un riferimento, da creare.  
  
 `nRank`  
 in Rango (ovvero, numero di dimensioni) della matrice. Questo valore deve essere 0 se `elementType` specifica un puntatore o un tipo di riferimento.  
  
 `pTypeArg`  
 in Puntatore a un oggetto ICorDebugType che rappresenta il tipo di matrice, puntatore o riferimento da creare.  
  
 `ppType`  
 out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta la matrice costruita, il tipo di puntatore o il tipo di riferimento.  
  
## <a name="remarks"></a>Osservazioni  
 Il valore di *elementType* deve essere uno dei seguenti:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY o ELEMENT_TYPE_SZARRAY  
  
 Se il valore di *elementType* è ELEMENT_TYPE_PTR o ELEMENT_TYPE_BYREF, *nRank* deve essere zero.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
