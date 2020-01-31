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
ms.openlocfilehash: cc5093a5ba0afcccaf960e9b8776f93a061cc2f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785675"
---
# <a name="_efn_stacktrace-function"></a>\_AAPN\_funzione StackTrace
Fornisce una rappresentazione testuale di una traccia dello stack gestito e una matrice di record `CONTEXT`, uno per ogni transizione tra codice non gestito e gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `Client`  
 in Client di cui è in corso il debug.  
  
 `wszTextOut`  
 out Rappresentazione testuale della traccia dello stack.  
  
 `puiTextLength`  
 out Puntatore al numero di caratteri in `wszTextOut`.  
  
 `pTransitionContexts`  
 out Matrice di contesti di transizione.  
  
 `puiTransitionContextCount`  
 out Puntatore al numero di contesti di transizione nella matrice.  
  
 `uiSizeOfContext`  
 in Dimensione della struttura del contesto.  
  
 `Flags`  
 in Impostare su 0 o SOS_STACKTRACE_SHOWADDRESSES (0x01) per visualizzare il registro EBP e il puntatore di stack di immissione (ESP) davanti a ogni riga di `module!functionname`.  
  
## <a name="remarks"></a>Note  
 La struttura di `_EFN_StackTrace` può essere chiamata da un'interfaccia WinDbg a livello di codice. I parametri vengono usati come indicato di seguito:  
  
- Se `wszTextOut` è null e `puiTextLength` non è null, la funzione restituisce la lunghezza della stringa in `puiTextLength`.  
  
- Se `wszTextOut` non è null, la funzione archivia il testo in `wszTextOut` fino alla posizione indicata da `puiTextLength`. Viene restituito correttamente se lo spazio disponibile nel buffer è sufficiente oppure restituisce E_OUTOFMEMORY se la lunghezza del buffer non è sufficiente.  
  
- La parte della funzione di transizione viene ignorata se `pTransitionContexts` e `puiTransitionContextCount` sono entrambi null. In questo caso, la funzione fornisce ai chiamanti l'output di testo solo dei nomi di funzione.  
  
- Se `pTransitionContexts` è null e `puiTransitionContextCount` non è null, la funzione restituisce il numero necessario di voci di contesto in `puiTransitionContextCount`.  
  
- Se `pTransitionContexts` non è null, la funzione lo considera come una matrice di strutture di lunghezza `puiTransitionContextCount`. La dimensione della struttura viene fornita da `uiSizeOfContext`e deve essere la dimensione di [SimpleContext](stacktrace-simplecontext-structure.md) o `CONTEXT` per l'architettura.  
  
- `wszTextOut` viene scritto nel formato seguente:  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- Se l'offset in esadecimale è 0x0, non viene scritto alcun offset.  
  
- Se non è presente codice gestito nel thread attualmente nel contesto, la funzione restituisce SOS_E_NOMANAGEDCODE.  
  
- Il parametro `Flags` è 0 o SOS_STACKTRACE_SHOWADDRESSES per vedere EBP ed ESP davanti a ogni riga di `module!functionname`. Per impostazione predefinita, è 0.  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali di debug](debugging-global-static-functions.md)
