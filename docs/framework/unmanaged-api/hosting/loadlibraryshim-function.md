---
title: Funzione LoadLibraryShim
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ab44ce8f51620d83084d1dd16e98b2b310feb76
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968934"
---
# <a name="loadlibraryshim-function"></a>Funzione LoadLibraryShim
Carica una versione specificata di una DLL inclusa nel pacchetto ridistribuibile .NET Framework.  
  
 Questa funzione è stata deprecata nel .NET Framework 4. Usare invece il metodo [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szDllName`  
 in Stringa con terminazione zero che rappresenta il nome della DLL da caricare dalla libreria .NET Framework.  
  
 `szVersion`  
 in Stringa con terminazione zero che rappresenta la versione della DLL da caricare. Se `szVersion` è null, la versione selezionata per il caricamento è la versione più recente della DLL specificata inferiore alla versione 4. Ovvero tutte le versioni uguale o superiore alla versione 4 vengono ignorate se `szVersion` è null e se non è installata alcuna versione precedente alla versione 4, il caricamento della dll non riesce. In questo modo si garantisce che l'installazione di .NET Framework 4 non influisca sulle applicazioni o sui componenti preesistenti. Vedere la voce relativa [a SxS e migrazione avvio rapido](https://go.microsoft.com/fwlink/?LinkId=200329) nel Blog del team CLR.  
  
 `pvReserved`  
 Riservato per usi futuri.  
  
 `phModDll`  
 out Puntatore all'handle del modulo.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti.  
  
|Codice restituito|DESCRIZIONE|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|CLR_E_SHIM_RUNTIMELOAD|Il `szDllName` caricamento richiede il caricamento del Common Language Runtime (CLR) e non è possibile caricare la versione necessaria di CLR.|  
  
## <a name="remarks"></a>Note  
 Questa funzione viene utilizzata per caricare le DLL incluse nel pacchetto ridistribuibile .NET Framework. Non carica le DLL generate dall'utente.  
  
> [!NOTE]
> A partire dalla versione .NET Framework 2,0, il caricamento di Fusion. dll causa il caricamento di CLR. Ciò è dovuto al fatto che le funzioni in Fusion. dll sono ora wrapper le cui implementazioni vengono fornite dal runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
