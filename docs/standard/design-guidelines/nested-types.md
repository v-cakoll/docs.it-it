---
title: Tipi nidificati
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
ms.openlocfilehash: dd13116b13ac8e2d7a3af6ef014eb4f393909515
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743694"
---
# <a name="nested-types"></a>Tipi nidificati
Un tipo annidato è un tipo definito nell'ambito di un altro tipo, denominato tipo di inclusione. Un tipo annidato può accedere a tutti i membri del relativo tipo di inclusione. Ad esempio, ha accesso ai campi privati definiti nel tipo di inclusione e ai campi protetti definiti in tutti i predecessori del tipo di inclusione.

 In generale, i tipi annidati devono essere usati sporadicamente. Le ragioni sono molteplici. Alcuni sviluppatori non hanno familiarità con il concetto. Questi sviluppatori potrebbero, ad esempio, presentare problemi con la sintassi della dichiarazione di variabili di tipi annidati. I tipi annidati sono anche strettamente collegati ai tipi di inclusione e, di conseguenza, non sono adatti per essere tipi generici.

 I tipi annidati sono particolarmente adatti per i dettagli di implementazione della modellazione dei relativi tipi di inclusione. L'utente finale deve raramente dichiarare le variabili di un tipo annidato e quasi mai dovrebbe dover creare esplicitamente un'istanza di tipi annidati. Ad esempio, l'enumeratore di una raccolta può essere un tipo annidato di tale raccolta. Gli enumeratori vengono in genere creati in base al tipo di inclusione e poiché molti linguaggi supportano l'istruzione foreach, le variabili di enumeratore devono essere dichiarate raramente dall'utente finale.

 ✔️ utilizzare tipi annidati quando la relazione tra il tipo annidato e il relativo tipo esterno è tale che sia auspicabile la semantica di accessibilità dei membri.

 ❌ non utilizzano tipi annidati pubblici come costrutto di raggruppamento logico; usare gli spazi dei nomi per questo.

 ❌ evitare tipi annidati esposti pubblicamente. L'unica eccezione è rappresentata dal caso in cui le variabili del tipo annidato debbano essere dichiarate solo in rari scenari, ad esempio la sottoclasse o altri scenari di personalizzazione avanzati.

 ❌ non utilizzano tipi annidati se è probabile che al tipo venga fatto riferimento all'esterno del tipo che lo contiene.

 Ad esempio, un'enumerazione passata a un metodo definito in una classe non deve essere definita come tipo annidato nella classe.

 ❌ non utilizzano tipi annidati se è necessario creare un'istanza del codice client.  Se un tipo dispone di un costruttore pubblico, probabilmente non dovrebbe essere annidato.

 Se è possibile creare un'istanza di un tipo, questo sembra indicare che il tipo ha una posizione nel Framework autonomo (è possibile crearla, usarla ed eliminarla senza mai usare il tipo esterno) e pertanto non deve essere annidata. I tipi interni non devono essere ampiamente riutilizzati all'esterno del tipo esterno senza alcuna relazione con il tipo esterno.

 ❌ non definiscono un tipo annidato come membro di un'interfaccia. Molti linguaggi non supportano un costrutto di questo tipo.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
