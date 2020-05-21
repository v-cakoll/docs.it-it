---
title: Metodo ICLRRuntimeInfo::GetVersionString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
ms.openlocfilehash: ccf48b6aea25bd602b55727c2e5958811702f6bf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762578"
---
# <a name="iclrruntimeinfogetversionstring-method"></a>Metodo ICLRRuntimeInfo::GetVersionString
Ottiene le informazioni sulla versione di Common Language Runtime (CLR) associate a un'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) specificata.  
  
 Questo metodo sostituisce le funzioni seguenti:  
  
- [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)  
  
- [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzBuffer`  
 out La versione di compilazione .NET Framework nel formato "v*a*. *B*[.* X*] ". *A*, *B*e *X* sono numeri decimali che corrispondono alla versione principale, alla versione secondaria e al numero di Build. *X* è facoltativo. Se *X* non è presente, non esiste alcun punto finale.  
  
> [!NOTE]
> Questo parametro deve corrispondere al nome della directory per la versione .NET Framework, come appare in C:\Windows\Microsoft.NET\Framework.  
  
 I valori di esempio sono "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" e "v 4.0. *x*", dove *x* dipende dal numero di build installato. Si noti che il prefisso "v" è obbligatorio.  
  
 `pchBuffer`  
 [in, out] Specifica la dimensione di `pwzBuffer` per evitare sovraccarichi del buffer. Se `pwzBuffer` è `null` , `pchBuffer` restituisce la dimensione richiesta di `pwzBuffer` per consentire la preallocazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzBuffer` o `pchBuffer` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosting](index.md)
