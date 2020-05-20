---
title: Funzione _CorDllMain
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: 3b2322f708afed08172f87e843c225aa9c60d9d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616606"
---
# <a name="_cordllmain-function"></a>\_CorDllMain (funzione)

Inizializza il Common Language Runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e avvia l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hInst`  
 in Handle dell'istanza del modulo caricato.  
  
 `dwReason`  
 in Indica il motivo per cui viene chiamata la funzione del punto di ingresso della DLL. Questo parametro può essere uno dei valori seguenti: DLL \_ PROCESS_ATTACH, \_ collegamento thread dll \_ , \_ collegamento thread dll \_ o \_ disconnessione processo dll \_ . Per una descrizione di questi valori, vedere la `DllMain` documentazione in Platform SDK.  
  
 `lpReserved`  
 [in] Non utilizzato.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce `true` per l'esito positivo e `false` se si verifica un errore.  
  
## <a name="remarks"></a>Osservazioni  
 Questa funzione viene chiamata dal caricatore del sistema operativo per gli assembly DLL. Per gli assembly eseguibili, il caricatore chiama invece la funzione [ \_ CorExeMain](corexemain-function.md) .  
  
 Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file DLL.  
  
La `_CorDllMain` funzione viene chiamata direttamente dal caricatore del sistema operativo.
  
 Per ulteriori informazioni, vedere la sezione osservazioni nell'argomento [ \_ CorValidateImage](corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Requisiti  

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../metadata/metadata-global-static-functions.md)
