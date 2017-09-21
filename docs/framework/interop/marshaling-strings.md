---
title: Marshalling di stringhe
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- marshaling, samples
- platform invoke, marshaling data
- data marshaling, strings
- data marshaling, samples
- data marshaling, platform invoke
- marshaling. strings
- marshaling, platform invoke
- sample applications [.NET Framework], marshaling strings
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8d8455d4f1b4dbb463176c06d680b2bd0b1ff9d9
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="marshaling-strings"></a>Marshalling di stringhe
Platform invoke copia parametri stringa, convertendoli dal formato .NET Framework (Unicode) al formato non gestito (ANSI) all'occorrenza. Dato che le stringhe gestite non sono modificabili, platform invoke non le copia di nuovo dalla memoria non gestita alla memoria gestita quando la funzione restituisce il controllo.  
  
 La tabella seguente elenca le opzioni di marshalling per le stringhe con la descrizione dell'utilizzo e un collegamento all'esempio .NET Framework corrispondente.  
  
|String|Descrizione|Esempio|  
|------------|-----------------|------------|  
|Per valore.|Passa le stringhe come parametri in.|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|Come risultato.|Restituisce le stringhe da codice non gestito.|[Stringhe](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|Per riferimento.|Passa le strutture come parametri in/out tramite <xref:System.Text.StringBuilder>.|[Buffer](http://msdn.microsoft.com/en-us/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|In una struttura per valore.|Passa le stringhe in una struttura che è un parametro in.|[Struct](http://msdn.microsoft.com/en-us/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|In una struttura per riferimento **(char\*)**.|Passa le stringhe in una struttura che è un parametro in/out. La funzione non gestita prevede un puntatore a un buffer di caratteri e le dimensioni del buffer sono un membro della struttura.|[Stringhe](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|In una struttura per riferimento **(char[])**.|Passa le stringhe in una struttura che è un parametro in/out. La funzione non gestita prevede un buffer di caratteri incorporati.|[OSInfo](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|In una classe per valore **(char\*)**.|Passa le stringhe in una classe (una classe è un parametro in/out). La funzione non gestita prevede un puntatore a un buffer di caratteri.|[OpenFileDlg](http://msdn.microsoft.com/en-us/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|In una classe per valore **(char[])**.|Passa le stringhe in una classe (una classe è un parametro in/out). La funzione non gestita prevede un buffer di caratteri incorporati.|[OSInfo](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|Come matrice di stringhe per valore.|Crea una matrice di stringhe passata per valore.|[Array](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|Come matrice di strutture che contengono le stringhe per valore.|Crea una matrice di strutture che contengono le stringhe e la matrice viene passata per valore.|[Array](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>Vedere anche  
 [Marshalling dei dati con platform invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)   
 [Tipi di dati platform invoke](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Marshalling di classi, strutture e unioni](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)   
 [Marshalling di matrici di tipi](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)   
 [Esempi vari di marshalling](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)

