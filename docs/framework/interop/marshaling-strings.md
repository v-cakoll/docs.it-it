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
ms.openlocfilehash: 88b6342038f99bf06fa2986c43f422e63cffd31e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124386"
---
# <a name="marshaling-strings"></a>Marshalling di stringhe
Platform invoke copia parametri stringa, convertendoli dal formato .NET Framework (Unicode) al formato non gestito (ANSI) all'occorrenza. Dato che le stringhe gestite non sono modificabili, platform invoke non le copia di nuovo dalla memoria non gestita alla memoria gestita quando la funzione restituisce il controllo.  
  
 La tabella seguente elenca le opzioni di marshalling per le stringhe con la descrizione dell'utilizzo e un collegamento all'esempio .NET Framework corrispondente.  
  
|string|Descrizione|Esempio|  
|------------|-----------------|------------|  
|Per valore.|Passa le stringhe come parametri in.|[MsgBox](msgbox-sample.md)|  
|Come risultato.|Restituisce le stringhe da codice non gestito.|[Stringhe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e765dyyy(v=vs.100))|  
|Per riferimento.|Passa le strutture come parametri in/out tramite <xref:System.Text.StringBuilder>.|[Buffer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100))|  
|In una struttura per valore.|Passa le stringhe in una struttura che è un parametro in.|[Struct](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100))|  
|In una struttura per riferimento **(char\*)**.|Passa le stringhe in una struttura che è un parametro in/out. La funzione non gestita prevede un puntatore a un buffer di caratteri e le dimensioni del buffer sono un membro della struttura.|[Stringhe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e765dyyy(v=vs.100))|  
|In una struttura per riferimento **(char[])**.|Passa le stringhe in una struttura che è un parametro in/out. La funzione non gestita prevede un buffer di caratteri incorporati.|[OSInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))|  
|In una classe per valore **(char\*)**.|Passa le stringhe in una classe (una classe è un parametro in/out). La funzione non gestita prevede un puntatore a un buffer di caratteri.|[OpenFileDlg](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w5tyztk9(v=vs.100))|  
|In una classe per valore **(char[])**.|Passa le stringhe in una classe (una classe è un parametro in/out). La funzione non gestita prevede un buffer di caratteri incorporati.|[OSInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))|  
|Come matrice di stringhe per valore.|Crea una matrice di stringhe passata per valore.|[Matrici](marshaling-different-types-of-arrays.md)|  
|Come matrice di strutture che contengono le stringhe per valore.|Crea una matrice di strutture che contengono le stringhe e la matrice viene passata per valore.|[Matrici](marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>Vedere anche

- [Marshalling predefinito per le stringhe](default-marshaling-for-strings.md)
- [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md)
- [Marshalling di classi, strutture e unioni](marshaling-classes-structures-and-unions.md)
- [Marshalling di diversi tipi di matrici](marshaling-different-types-of-arrays.md)
- [Esempi vari di marshalling](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))
