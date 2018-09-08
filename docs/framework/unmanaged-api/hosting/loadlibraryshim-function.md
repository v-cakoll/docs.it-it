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
ms.openlocfilehash: 5fe1ba15f8a9f8ee79582158209049c1e502a61d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211684"
---
# <a name="loadlibraryshim-function"></a>Funzione LoadLibraryShim
Carica una versione specifica di una DLL che è incluso nel pacchetto ridistribuibile di .NET Framework.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Usare la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szDllName`  
 [in] Una stringa con terminazione zero che rappresenta il nome della DLL da caricare dalla libreria di .NET Framework.  
  
 `szVersion`  
 [in] Una stringa con terminazione zero che rappresenta la versione della DLL da caricare. Se `szVersion` è null, la versione selezionata per il caricamento è la versione più recente del file DLL specificata che è inferiore alla versione 4. Vale a dire tutte le versioni uguale o maggiore della versione 4 vengono ignorate se `szVersion` è null, e se non è installata alcuna versione inferiore alla versione 4, la DLL non riesce a caricare. Questo modo si garantisce che l'installazione del [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] non influiscono sulle applicazioni preesistenti o componenti. Vedere l'intervento [SxS In-Process e avvio rapido di migrazione](https://go.microsoft.com/fwlink/?LinkId=200329) nel blog del team CLR.  
  
 `pvReserved`  
 Riservato per utilizzi futuri.  
  
 `phModDll`  
 [out] Un puntatore all'handle del modulo.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore standard modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|CLR_E_SHIM_RUNTIMELOAD|Il caricamento `szDllName` richiede il caricamento non è possibile caricare common language runtime (CLR) e la versione necessaria di CLR.|  
  
## <a name="remarks"></a>Note  
 Questa funzione viene utilizzata per caricare le DLL incluse nel pacchetto ridistribuibile di .NET Framework. Non è possibile caricare le DLL generati dall'utente.  
  
> [!NOTE]
>  A partire da .NET Framework versione 2.0, il caricamento Fusion fa sì che Common Language Runtime da caricare. Questo avviene perché le funzioni in Fusion. dll sono ora le cui implementazioni sono fornite dal runtime del wrapper.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
