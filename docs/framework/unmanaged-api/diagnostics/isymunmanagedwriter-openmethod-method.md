---
title: Metodo ISymUnmanagedWriter::OpenMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: d2d16ab0a29fadd3a64d906a64fc46c422e01c45
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610041"
---
# <a name="isymunmanagedwriteropenmethod-method"></a>Metodo ISymUnmanagedWriter::OpenMethod
Apre un metodo in cui vengono emesse le informazioni sui simboli. Il metodo specificato diventa il metodo corrente per le chiamate a per definire i punti di sequenza, i parametri e gli ambiti lessicali. È presente un ambito lessicale implicito intorno all'intero metodo. La riapertura di un metodo precedentemente chiuso Cancella tutti i simboli definiti in precedenza per il metodo. Può essere presente un solo metodo Open alla volta.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a>Parametri  
 `method`  
 in Token di metadati per il metodo da aprire.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Metodo CloseMethod](isymunmanagedwriter-closemethod-method.md)
- [Metodo OpenMethod2](isymunmanagedwriter3-openmethod2-method.md)
