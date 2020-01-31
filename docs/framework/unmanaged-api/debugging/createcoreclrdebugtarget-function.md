---
title: Funzione CreateCoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: a7fed8cb70785f0ccfcadf1e16181db303ac98e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789187"
---
# <a name="createcoreclrdebugtarget-function"></a>Funzione CreateCoreClrDebugTarget
Crea una connessione a un proxy del debugger in esecuzione su un computer remoto e restituisce un oggetto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) che può essere usato per eseguire query sui processi in esecuzione e sui runtime caricati nel computer remoto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAddress`  
 [in] Indirizzo IPv4 di un computer di destinazione remoto.  
  
 `ppTarget`  
 out Puntatore a un puntatore a un oggetto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) che verrà creato.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.  
  
 E_OUTOFMEMORY  
 Non è possibile allocare memoria sufficiente per `ppTarget`.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Altri errori.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Libreria:** mscordbi_macx86. dll  
  
 **Versioni .NET Framework:** 3,5 SP1
