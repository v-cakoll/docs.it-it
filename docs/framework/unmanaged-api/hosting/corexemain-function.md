---
title: Funzione _CorExeMain
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
ms.openlocfilehash: 935ac478fb966315e81fdcc004761038b28e3178
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616591"
---
# <a name="_corexemain-function"></a>Funzione _CorExeMain
Inizializza il Common Language Runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e avvia l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Osservazioni  
 Questa funzione viene chiamata dal caricatore nei processi creati dagli assembly eseguibili gestiti. Per gli assembly DLL, il caricatore chiama invece la funzione [_CorDllMain](cordllmain-function.md) .  
  
 Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file di immagine.  
  
 In Windows 98, Windows ME, Windows NT e Windows 2000, la `_CorExeMain` funzione viene chiamata indirettamente tramite una correzione nel caricatore del sistema operativo. In tutte le altre versioni di Windows, viene chiamato direttamente dal caricatore del sistema operativo.  
  
 Per ulteriori informazioni, vedere la sezione osservazioni nell'argomento [_CorValidateImage](corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../metadata/metadata-global-static-functions.md)
