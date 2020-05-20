---
title: Metodo ICLRErrorReportingManager::BeginCustomDump
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
ms.openlocfilehash: 4c83ffaf920abe005ba987e0a744e13aa0d3c016
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615670"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>Metodo ICLRErrorReportingManager::BeginCustomDump
Specifica la configurazione dei dump dell'heap personalizzati per la segnalazione degli errori.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwFlavor`  
 in Valore [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) che indica il tipo di dump dell'heap su cui compilare il dump dell'heap personalizzato.  
  
 `dwNumItems`  
 in Lunghezza della `items` matrice. Se `dwFlavor` non è DUMP_FLAVOR_Mini, `dwNumItems` deve essere zero.  
  
 `items`  
 in Matrice di istanze di [CustomDumpItem](customdumpitem-structure.md) , che specifica gli elementi da aggiungere al minidump. Se `dwFlavor` non è DUMP_FLAVOR_Mini, `items` deve essere null.  
  
 `dwReserved`  
 [in] Riservato per un utilizzo futuro.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Il metodo è stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `BeginCustomDump` metodo imposta la configurazione del dump dell'heap personalizzato. Il metodo [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) Cancella la configurazione del dump dell'heap personalizzato e libera qualsiasi stato associato. Deve essere chiamato dopo il completamento del dump dell'heap personalizzato.  
  
> [!IMPORTANT]
> La mancata chiamata `EndCustomDump` causa la perdita della memoria.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Struttura CustomDumpItem](customdumpitem-structure.md)
- [Enumerazione ECustomDumpFlavor](ecustomdumpflavor-enumeration.md)
- [Interfaccia ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)
