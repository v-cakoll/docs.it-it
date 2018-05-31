---
title: Marshalling di stringhe
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52a78e0c3969e879bf2fd1b1f5c41b2caac2ba11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391121"
---
# <a name="marshaling-strings"></a>Marshalling di stringhe
Platform invoke copia parametri stringa, convertendoli dal formato .NET Framework (Unicode) al formato non gestito (ANSI) all'occorrenza. Dato che le stringhe gestite non sono modificabili, platform invoke non le copia di nuovo dalla memoria non gestita alla memoria gestita quando la funzione restituisce il controllo.  
  
 La tabella seguente elenca le opzioni di marshalling per le stringhe con la descrizione dell'utilizzo e un collegamento all'esempio .NET Framework corrispondente.  
  
|Stringa|Descrizione|Esempio|  
|------------|-----------------|------------|  
|Per valore.|Passa le stringhe come parametri in.|[MsgBox](msgbox-sample.md)|  
|Come risultato.|Restituisce le stringhe da codice non gestito.|[Stringhe](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))|  
|Per riferimento.|Passa le strutture come parametri in/out tramite <xref:System.Text.StringBuilder>.|[Buffer](https://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5(v=vs.100))|  
|In una struttura per valore.|Passa le stringhe in una struttura che è un parametro in.|[Struct](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100))|  
|In una struttura per riferimento **(char\*)**.|Passa le stringhe in una struttura che è un parametro in/out. La funzione non gestita prevede un puntatore a un buffer di caratteri e le dimensioni del buffer sono un membro della struttura.|[Stringhe](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))|  
|In una struttura per riferimento **(char[])**.|Passa le stringhe in una struttura che è un parametro in/out. La funzione non gestita prevede un buffer di caratteri incorporati.|[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))|  
|In una classe per valore **(char\*)**.|Passa le stringhe in una classe (una classe è un parametro in/out). La funzione non gestita prevede un puntatore a un buffer di caratteri.|[OpenFileDlg](https://msdn.microsoft.com/library/b7dea792-cb92-4baf-ac7b-6a24803e6c75(v=vs.100))|  
|In una classe per valore **(char[])**.|Passa le stringhe in una classe (una classe è un parametro in/out). La funzione non gestita prevede un buffer di caratteri incorporati.|[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))|  
|Come matrice di stringhe per valore.|Crea una matrice di stringhe passata per valore.|[Array](marshaling-different-types-of-arrays.md)|  
|Come matrice di strutture che contengono le stringhe per valore.|Crea una matrice di strutture che contengono le stringhe e la matrice viene passata per valore.|[Array](marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>Vedere anche  
 [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md)  
 [Tipi di dati platform invoke](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))  
 [Marshalling di classi, strutture e unioni](marshaling-classes-structures-and-unions.md)  
 [Marshalling di matrici di tipi](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))  
 [Esempi vari di marshalling](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))
