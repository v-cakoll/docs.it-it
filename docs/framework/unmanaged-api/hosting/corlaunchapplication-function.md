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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f2a05009caed7bef6da9edee57a4a54b876b18f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580993"
---
# <a name="corlaunchapplication-function"></a>Funzione CorLaunchApplication
Avvia l'applicazione nel percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `dwClickOnceHost`  
 [in] Valore di [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumerazione che specifica il tipo di host che è l'avvio dell'applicazione.  
  
 `pwzAppFullName`  
 [in] Il nome completo dell'applicazione in corso di avvio.  
  
 `dwManifestPaths`  
 [in] Il numero di percorsi di manifesto dell'applicazione.  
  
 `ppwzManifestPaths`  
 [in] Matrice di stringhe, ognuna delle quali specifica un percorso di un manifesto dell'applicazione in corso di avvio.  
  
 `dwActivationData`  
 [in] Il numero di elementi di dati di attivazione per l'applicazione in corso di avvio.  
  
 `ppwzActivationData`  
 [in] Matrice di stringhe, ognuna delle quali è un elemento di dati di attivazione per l'applicazione in corso di avvio.  
  
 `lpProcessInformation`  
 [out] Puntatore alle informazioni sul processo in cui è stata caricata l'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
