---
title: Funzione CreateVersionStringFromModule
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
ms.openlocfilehash: 609d6e47c951aa104cb23084b65e98827a6851f1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789182"
---
# <a name="createversionstringfrommodule-function"></a>Funzione CreateVersionStringFromModule
Crea una stringa di versione da un percorso Common Language Runtime (CLR) in un processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pidDebuggee`  
 [in] Identificatore del processo nel quale è caricato il CLR di destinazione.  
  
 `szModuleName`  
 [in] Percorso completo o relativo del CLR di destinazione caricato nel processo.  
  
 `pBuffer`  
 [out] Buffer di ritorno per l'archiviazione delle stringhe di versione per il CLR di destinazione.  
  
 `cchBuffer`  
 [in] Dimensione di `pBuffer`.  
  
 `pdwLength`  
 [out] Lunghezza della stringa di versione restituita da `pBuffer`.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 La stringa della versione per il CLR di destinazione è stata correttamente restituita in `pBuffer`.  
  
 E_INVALIDARG  
 `szModuleName` è null oppure either `pBuffer` o `cchBuffer` è null. `pBuffer` e `cchBuffer` devono entrambi essere null o non Null.  
  
 HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)  
 `pdwLength` è maggiore di `cchBuffer`. Può trattarsi di un risultato previsto se è stato passato un valore Null per entrambi gli elementi `pBuffer` e `cchBuffer` e se è stata eseguita una query sulle dimensioni del buffer necessarie tramite `pdwLength`.  
  
 HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)  
 `szModuleName` on contiene un percorso a un CLR valido nel processo di destinazione.  
  
 E_FAIL (o altri codici E_ restituiti)  
 `pidDebuggee` non fa riferimento a un processo valido o a altri errori.  
  
## <a name="remarks"></a>Note  
 Questa funzione accetta un processo di CLR identificato da `pidDebuggee` e un percorso della stringa specificato da `szModuleName`. La stringa della versione viene restituita nel buffer al quale punta`pBuffer`. Questa stringa è invisibile all'utente della funzione. In altre parole, non è presente alcun significato intrinseco nella stringa di versione stessa. Viene utilizzato esclusivamente nel contesto di questa funzione e della [funzione CreateDebuggingInterfaceFromVersion](createdebugginginterfacefromversion-function-for-silverlight.md).  
  
 Questa funzione deve essere chiamata due volte. Quando si chiama per la prima volta, passare il valore null per `pBuffer` e `cchBuffer`. Quando si esegue questa operazione, le dimensioni del buffer necessarie per `pBuffer` verranno restituite in `pdwLength`. È possibile, quindi, chiamare la funzione una seconda volta e passare il buffer in `pBuffer` e le sue dimensioni in `cchBuffer`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** dbgshim. h  
  
 **Libreria:** dbgshim. dll  
  
 **Versioni .NET Framework:** 3,5 SP1
