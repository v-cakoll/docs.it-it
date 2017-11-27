---
title: Funzione _CorDllMain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorDllMain
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorDllMain
helpviewer_keywords: _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2e4188f8b95141118e4bbb2df2a702ff04c2adf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cordllmain-function"></a>Funzione _CorDllMain
Consente di inizializzare common language runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e inizia l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `hInst`  
 [in] L'handle dell'istanza del modulo caricato.  
  
 `dwReason`  
 [in] Indica i motivi per cui viene richiamata la funzione di punto di ingresso DLL. Questo parametro può essere uno dei seguenti valori: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH o DLL_PROCESS_DETACH. Per una descrizione di questi valori, vedere il `DllMain` documentazione di Platform SDK.  
  
 `lpReserved`  
 [in] Non usato.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce `true` per l'esito positivo e `false` se si verifica un errore.  
  
## <a name="remarks"></a>Note  
 Questa funzione viene chiamata dal caricatore del sistema operativo per gli assembly DLL. Per gli assembly eseguibili, il caricatore chiama la [CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funzione alternativa.  
  
 Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file DLL.  
  
 In Windows 98, Windows ME, Windows NT e Windows 2000, la `_CorDllMain` funzione viene chiamata indirettamente tramite una fixupin caricatore del sistema operativo. In tutte le altre versioni di Windows, viene chiamato direttamente dal caricatore del sistema operativo.  
  
 Per ulteriori informazioni, vedere la sezione osservazioni nel [CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) argomento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
