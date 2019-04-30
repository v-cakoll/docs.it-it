---
title: Metodo ICorDebugFunction2::EnumerateNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4d15d9ae63e63f98ab73e250df558dfa16002a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959965"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>Metodo ICorDebugFunction2::EnumerateNativeCode
Ottiene un puntatore a interfaccia a un oggetto ICorDebugCodeEnum contenente le istruzioni di codice nativo nella funzione di cui viene fatto riferimento dall'oggetto ICorDebugFunction2.  
  
> [!NOTE]
>  `EnumerateNativeCode` non è implementata nella versione corrente di .NET Framework.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorDebug.idl, CorDebug.h
