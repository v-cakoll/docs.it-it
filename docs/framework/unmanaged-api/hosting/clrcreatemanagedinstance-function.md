---
title: Funzione ClrCreateManagedInstance
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: ecd618ecf08836ea5e38ce738f97fc91ee6426f4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616814"
---
# <a name="clrcreatemanagedinstance-function"></a>Funzione ClrCreateManagedInstance
Crea un'istanza del tipo gestito specificato.  
  
 Questa funzione è stata deprecata nel .NET Framework 4. Utilizzare l'attivazione COM per creare un'istanza del tipo gestito oppure utilizzare l'hosting (vedere [le interfacce di hosting CLR aggiunte in .NET Framework 4 e 4,5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pTypeName`  
 in Puntatore al nome del tipo di istanza richiesto.  
  
 `riid`  
 in Oggetto `IID` del tipo di istanza richiesto.  
  
 `ppObject`  
 out Puntatore a un puntatore a un'istanza del tipo gestito richiesta dal chiamante.  
  
## <a name="remarks"></a>Osservazioni  
 Il Common Language Runtime deve essere già caricato in un processo. Ad esempio, può essere caricata utilizzando una chiamata alla funzione [CorBindToRuntimeEx](corbindtoruntimeex-function.md) prima che `ClrCreateManagedInstance` venga chiamata la funzione. Se il runtime non è caricato, `ClrCreateManagedInstance` tenta innanzitutto di caricare v 1.0.3705 del runtime. Se l'operazione ha esito negativo, tenta di caricare la versione più recente del runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
- [Hosting](index.md)
