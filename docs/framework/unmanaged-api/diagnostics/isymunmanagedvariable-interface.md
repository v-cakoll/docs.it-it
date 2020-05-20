---
title: Interfaccia ISymUnmanagedVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610171"
---
# <a name="isymunmanagedvariable-interface"></a>Interfaccia ISymUnmanagedVariable
Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetAddressField1](isymunmanagedvariable-getaddressfield1-method.md)|Ottiene il primo campo dell'indirizzo per questa variabile. Il suo significato dipende dal tipo di indirizzo.|  
|[Metodo GetAddressField2](isymunmanagedvariable-getaddressfield2-method.md)|Ottiene il secondo campo dell'indirizzo per questa variabile. Il suo significato dipende dal tipo di indirizzo.|  
|[Metodo GetAddressField3](isymunmanagedvariable-getaddressfield3-method.md)|Ottiene il terzo campo dell'indirizzo per questa variabile. Il suo significato dipende dal tipo di indirizzo.|  
|[Metodo GetAddressKind](isymunmanagedvariable-getaddresskind-method.md)|Ottiene il tipo di indirizzo della variabile.|  
|[Metodo GetAttributes](isymunmanagedvariable-getattributes-method.md)|Ottiene i flag di attributo per questa variabile.|  
|[Metodo GetEndOffset](isymunmanagedvariable-getendoffset-method.md)|Ottiene l'offset finale della variabile all'interno dell'elemento padre.|  
|[Metodo GetName](isymunmanagedvariable-getname-method.md)|Ottiene il nome della variabile.|  
|[Metodo GetSignature](isymunmanagedvariable-getsignature-method.md)|Ottiene la firma di questa variabile.|  
|[Metodo GetStartOffset](isymunmanagedvariable-getstartoffset-method.md)|Ottiene l'offset iniziale della variabile all'interno dell'elemento padre.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
