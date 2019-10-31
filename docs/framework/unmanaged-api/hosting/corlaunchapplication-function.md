---
title: Funzione CorLaunchApplication
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
ms.openlocfilehash: e01698d2d8491b2496bb664c13dca97964cd1481
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136941"
---
# <a name="corlaunchapplication-function"></a>Funzione CorLaunchApplication
Avvia l'applicazione nel percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwClickOnceHost`  
 in Valore dell'enumerazione [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) che specifica il tipo di host che sta avviando l'applicazione.  
  
 `pwzAppFullName`  
 in Nome completo dell'applicazione in fase di avvio.  
  
 `dwManifestPaths`  
 in Numero di percorsi del manifesto per l'applicazione.  
  
 `ppwzManifestPaths`  
 in Matrice di stringhe, ognuna delle quali specifica un percorso di un manifesto per l'applicazione in fase di avvio.  
  
 `dwActivationData`  
 in Numero di elementi di dati di attivazione per l'applicazione in fase di avvio.  
  
 `ppwzActivationData`  
 in Una matrice di stringhe, ognuna delle quali è un elemento di dati di attivazione per l'applicazione che viene avviata.  
  
 `lpProcessInformation`  
 out Puntatore alle informazioni sul processo in cui è stata caricata l'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
