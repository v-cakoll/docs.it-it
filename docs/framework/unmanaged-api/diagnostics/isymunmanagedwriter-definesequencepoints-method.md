---
title: Metodo ISymUnmanagedWriter::DefineSequencePoints
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e1dcc427a6d034ce108ca66f71cc24b1050a72f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>Metodo ISymUnmanagedWriter::DefineSequencePoints
Definisce un gruppo di punti di sequenza nel metodo corrente. Ogni riga e colonna iniziale definisce l'inizio di un'istruzione all'interno di un metodo. Ogni riga e colonna finale definisce la fine di un'istruzione all'interno di un metodo. Le matrici devono essere ordinate in ordine crescente di offset. L'offset viene sempre misurato dall'inizio del metodo, in byte.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `document`  
 [in] L'oggetto documento per il quale vengono definiti i punti di sequenza.  
  
 `spCount`  
 [in] Oggetto `ULONG32` che indica le dimensioni di ogni il `offsets`, `lines`, `columns`, `endLines`, e `endColumns` buffer.  
  
 `offsets`  
 [in] L'offset dei punti di sequenza misurato dall'inizio del metodo.  
  
 `lines`  
 [in] I numeri di riga iniziale dei punti di sequenza.  
  
 `columns`  
 [in] Numeri di colonna iniziali dei punti di sequenza.  
  
 `endLines`  
 [in] Numeri di riga finali dei punti di sequenza. Questo parametro è facoltativo.  
  
 `endColumns`  
 [in] Numeri di colonna finali dei punti di sequenza. Questo parametro è facoltativo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
