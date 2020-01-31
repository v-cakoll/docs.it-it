---
title: Funzione EnumerateCLRs
ms.date: 03/30/2017
api_name:
- EnumerateCLRs
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- EnumerateCLRs
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- EnumerateCLRs function
ms.assetid: f8d50cb3-ec4f-4529-8fe3-bd61fd28e13c
topic_type:
- apiref
ms.openlocfilehash: cdf88ef193df71a638fff43add1a9648d8631731
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789121"
---
# <a name="enumerateclrs-function"></a>Funzione EnumerateCLRs
Fornisce un meccanismo per l'enumerazione di CLR in un processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateCLRs (  
    [in]  DWORD      debuggeePID,  
    [out] HANDLE**   ppHandleArrayOut,  
    [out] LPWSTR**   ppStringArrayOut,  
    [out] DWORD*     pdwArrayLengthOut  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `debuggeePID`  
 [in] Identificatore del processo da cui verranno enumerati i CLR caricati.  
  
 `ppHandleArrayOut`  
 [out] Puntatore a una matrice contenente handle di evento usati per continuare un avvio di CLR. Non è garantito che ogni handle nella matrice sia valido. Se valido, l'handle deve essere usato come evento di avvio-continuazione per il rispettivo runtime presente nello stesso indice di `ppStringArrayOut`.  
  
 `ppStringArrayOut`  
 [out] Puntatore a una matrice di stringhe che specificano i percorsi completi di CLR caricati nel processo.  
  
 `pdwArrayLengthOut`  
 [out] Puntatore a un valore DWORD che contiene la lunghezza di `ppHandleArrayOut` e `pdwArrayLengthOut` con dimensioni identiche.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.  
  
 E_INVALIDARG  
 `ppHandleArrayOut` o `ppStringArrayOut` è Null oppure `pdwArrayLengthOut` è Null.  
  
 E_OUTOFMEMORY  
 La funzione non è in grado di allocare memoria sufficiente per le matrici di percorsi e di handle.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Impossibile enumerare i CLR caricati.  
  
## <a name="remarks"></a>Note  
 Per un processo di destinazione identificato da `debuggeePID`, la funzione restituisce una matrice di percorsi (`ppStringArrayOut`) ai CLR caricati nel processo, una matrice di handle di evento (`ppHandleArrayOut`) che può contenere un evento di avvio-continuazione del CLR per lo stesso indice, oltre alle dimensioni delle matrici (`pdwArrayLengthOut`) che specificano il numero di CLR caricati.  
  
 Nel sistema operativo Windows `debuggeePID` esegue il mapping a un identificatore di processo del sistema operativo.  
  
 La memoria per `ppHandleArrayOut` e `ppStringArrayOut` viene allocata da questa funzione. Per liberare la memoria allocata, è necessario chiamare la [funzione CloseCLREnumeration](closeclrenumeration-function.md).  
  
 Questa funzione può essere chiamata con entrambi i parametri di matrice impostati su Null per restituire il conteggio di CLR nel processo di destinazione. Da questo conteggio un chiamante è in grado di dedurre le dimensioni del buffer che verrà creato: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** dbgshim. h  
  
 **Libreria:** dbgshim. dll  
  
 **Versioni .NET Framework:** 3,5 SP1
