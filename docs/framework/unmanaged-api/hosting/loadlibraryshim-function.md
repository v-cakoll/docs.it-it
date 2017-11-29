---
title: Funzione LoadLibraryShim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LoadLibraryShim
helpviewer_keywords: LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c56f5a3576c505fd7b7d514e3f2d038e7f8f3ecc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="loadlibraryshim-function"></a>Funzione LoadLibraryShim
Carica una versione specifica di una DLL che è incluso nel pacchetto ridistribuibile di .NET Framework.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Utilizzare il [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) metodo invece.  
  
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
 [in] Stringa con terminazione zero che rappresenta il nome della DLL da caricare dalla libreria .NET Framework.  
  
 `szVersion`  
 [in] Stringa con terminazione zero che rappresenta la versione della DLL da caricare. Se `szVersion` è null, la versione selezionata per il caricamento è la versione più recente della DLL specificata che è inferiore alla versione 4. Vale a dire tutte le versioni uguale o maggiore della versione 4 vengono ignorate se `szVersion` è null, e se non è installata alcuna versione inferiore alla versione 4, è Impossibile caricare la DLL. In questo modo l'installazione di viene il [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] non influisce sul pre-esistente applicazioni o componenti. Vedere la voce [SxS In-Process e migrazione](http://go.microsoft.com/fwlink/?LinkId=200329) nel blog del team CLR.  
  
 `pvReserved`  
 Riservato per utilizzi futuri.  
  
 `phModDll`  
 [out] Un puntatore all'handle del modulo.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore standard del modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|CLR_E_SHIM_RUNTIMELOAD|Il caricamento `szDllName` richiede il caricamento non è possibile caricare common language runtime (CLR) e la versione necessaria di CLR.|  
  
## <a name="remarks"></a>Note  
 Questa funzione viene utilizzata per caricare le DLL che vengono inclusi nel pacchetto ridistribuibile di .NET Framework. Non è possibile caricare le DLL generati dall'utente.  
  
> [!NOTE]
>  A partire da .NET Framework versione 2.0, caricare il file Fusion.dll fa sì che Common Language Runtime da caricare. Questo avviene perché le funzioni in Fusion sono ora wrapper le cui implementazioni sono forniti dal runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di Hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
