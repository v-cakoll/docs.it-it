---
title: Funzione _EFN_StackTrace
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39a249108d10e5dc382775378e2d6b84bba87356
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408086"
---
# <a name="efnstacktrace-function"></a>Funzione _EFN_StackTrace
Fornisce una rappresentazione testuale di una traccia dello stack gestito e una matrice di record `CONTEXT`, uno per ogni transizione tra codice non gestito e gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `Client`  
 [in] Il client è in corso il debug.  
  
 `wszTextOut`  
 [out] La rappresentazione testo dell'analisi dello stack.  
  
 `puiTextLength`  
 [out] Un puntatore al numero di caratteri in `wszTextOut`.  
  
 `pTransitionContexts`  
 [out] Matrice di contesti di transizione.  
  
 `puiTransitionContextCount`  
 [out] Puntatore al numero di contesti di transizione nella matrice.  
  
 `uiSizeOfContext`  
 [in] Le dimensioni della struttura di contesto.  
  
 `Flags`  
 [in] Impostato su 0 o SOS_STACKTRACE_SHOWADDRESSES (0x01) per visualizzare il registro EBP e il puntatore dello stack invio (ESP) all'inizio di ogni `module!functionname` riga.  
  
## <a name="remarks"></a>Note  
 Il `_EFN_StackTrace` struttura può essere chiamata da un'interfaccia programmatica WinDbg. I parametri vengono utilizzati come indicato di seguito:  
  
-   Se `wszTextOut` è null e `puiTextLength` è non null, la funzione restituisce la lunghezza della stringa in `puiTextLength`.  
  
-   Se `wszTextOut` è non null, la funzione archivia il testo in `wszTextOut` fino alla posizione indicata da `puiTextLength`. Restituisce correttamente se non c'era disponibile spazio sufficiente nel buffer o restituisce E_OUTOFMEMORY se il buffer non è sufficiente.  
  
-   La parte relativa alla transizione della funzione viene ignorato se `pTransitionContexts` e `puiTransitionContextCount` sono entrambi null. In questo caso, la funzione fornisce un output di testo di solo i nomi di funzione.  
  
-   Se `pTransitionContexts` è null e `puiTransitionContextCount` è non null, la funzione restituisce il numero necessario di voci di contesto in `puiTransitionContextCount`.  
  
-   Se `pTransitionContexts` è non null, la funzione considera come una matrice di strutture con lunghezza `puiTransitionContextCount`. La dimensione della struttura viene fornita dalla `uiSizeOfContext`, e deve essere pari [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) o `CONTEXT` per l'architettura.  
  
-   `wszTextOut` viene scritto nel formato seguente:  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
-   Se l'offset in esadecimale è 0x0, viene scritto alcun offset.  
  
-   Se non è presente nessun codice gestito sul thread attualmente in contesto, la funzione restituisce SOS_E_NOMANAGEDCODE.  
  
-   Il `Flags` parametro è 0 o SOS_STACKTRACE_SHOWADDRESSES per visualizzare EBP ed ESP all'inizio di ogni `module!functionname` riga. Per impostazione predefinita è 0.  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
