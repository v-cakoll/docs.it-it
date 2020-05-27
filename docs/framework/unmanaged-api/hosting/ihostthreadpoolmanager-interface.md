---
title: Interfaccia IHostThreadPoolManager
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: bac29b5950f1547c5c60ac716d40d2ef4b1a2cc2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842480"
---
# <a name="ihostthreadpoolmanager-interface"></a>Interfaccia IHostThreadPoolManager
Fornisce metodi che consentono al Common Language Runtime (CLR) di configurare il pool di thread e di accodare gli elementi di lavoro al pool di thread.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md)|Ottiene il numero di thread nel pool di thread che non stanno attualmente elaborando elementi di lavoro.|  
|[Metodo GetMaxThreads](ihostthreadpoolmanager-getmaxthreads-method.md)|Ottiene il numero massimo di thread che l'host gestisce simultaneamente nel pool di thread.|  
|[Metodo GetMinThreads](ihostthreadpoolmanager-getminthreads-method.md)|Ottiene il numero minimo di thread inattivi gestiti dall'host in previsione di richieste.|  
|[Metodo QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)|Accoda una funzione per l'esecuzione e fornisce un oggetto contenente i dati che devono essere utilizzati dalla funzione.|  
|[Metodo SetMaxThreads](ihostthreadpoolmanager-setmaxthreads-method.md)|Imposta il numero massimo di thread che l'host è in grado di gestire nel pool di thread.|  
|[Metodo SetMinThreads](ihostthreadpoolmanager-setminthreads-method.md)|Imposta il numero minimo di thread inattivi che l'host deve gestire in previsione di richieste.|  
  
## <a name="remarks"></a>Osservazioni  
 L'host non è necessario per configurare il pool di thread usando i valori specificati nelle chiamate ai `SetMaxThreads` metodi e `SetMinThreads` . In questo caso, l'host deve restituire un valore HRESULT di E_NOTIMPL da questi metodi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Interfacce di hosting](hosting-interfaces.md)
