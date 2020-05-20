---
title: Interfaccia ISymUnmanagedReader2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: d4c5ff46d37b1292059b18920abd8042c18bbf31
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615397"
---
# <a name="isymunmanagedreader2-interface"></a>Interfaccia ISymUnmanagedReader2
Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli. Questa interfaccia estende l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetMethodByVersionPreRemap](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|Ottenere un metodo del lettore di simboli, dato un token del metodo e un numero di versione di modifica e continuazione.|  
|[Metodo GetMethodsInDocument](isymunmanagedreader2-getmethodsindocument-method.md)|Ottiene tutti i metodi che dispongono di informazioni sulla riga nel documento specificato.|  
|[Metodo GetSymAttributePreRemap](isymunmanagedreader2-getsymattributepreremap-method.md)|Ottiene un attributo personalizzato in base al nome.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedReader](isymunmanagedreader-interface.md)
