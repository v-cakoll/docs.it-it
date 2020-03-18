---
title: Progettazione di costruttori
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400603"
---
# <a name="constructor-design"></a>Progettazione di costruttori

Esistono due tipi di costruttori: costruttori di tipo e costruttori di istanza.

I costruttori di tipo sono statici e vengono eseguiti da CLR prima dell'utilizzo del tipo. I costruttori di istanza vengono eseguiti quando viene creata un'istanza di un tipo.

I costruttori di tipo non possono accettare parametri. I costruttori di istanza possono. I costruttori di istanza che non accettano parametri sono spesso denominati costruttori senza parametri.

I costruttori sono il modo più naturale per creare istanze di un tipo. La maggior parte degli sviluppatori cercherà e tenterà di utilizzare un costruttore prima di prendere in considerazione modi alternativi di creazione di istanze (ad esempio metodi factory).

✔️ CONSIDER che fornisce costruttori semplici e idealmente predefiniti.

Un costruttore semplice ha un numero molto ridotto di parametri e tutti i parametri sono primitive o enumerazioni. Tali costruttori semplici aumentano l'usabilità del framework.

✔️ CONSIDER utilizzando un metodo factory statico anziché un costruttore se la semantica dell'operazione desiderata non esegue direttamente il mapping alla costruzione di una nuova istanza o se le linee guida di progettazione del costruttore non sono innaturali.

✔️ utilizzare i parametri del costruttore come tasti di scelta rapida per l'impostazione delle proprietà principali.

Non dovrebbe esserci alcuna differenza nella semantica tra l'utilizzo del costruttore vuoto seguito da alcuni insiemi di proprietà e l'utilizzo di un costruttore con più argomenti.

✔️ utilizzare lo stesso nome per i parametri del costruttore e una proprietà se i parametri del costruttore vengono utilizzati per impostare semplicemente la proprietà.

L'unica differenza tra tali parametri e le proprietà dovrebbe essere maiuscole/minuscole.

✔️ lavoro minimo nel costruttore.

I costruttori non devono eseguire molte operazioni diverse dall'acquisizione dei parametri del costruttore. Il costo di qualsiasi altra elaborazione deve essere ritardato fino a quando richiesto.

✔️ generare eccezioni dai costruttori di istanza, se appropriato.

✔️ dichiarare in modo esplicito il costruttore pubblico senza parametri nelle classi, se tale costruttore è obbligatorio.

Se non si dichiarain modo esplicito i costruttori in un tipo, molti linguaggi (ad esempio, c'è) aggiungerà automaticamente un costruttore pubblico senza parametri. Le classi astratte ottengono un costruttore protetto.

L'aggiunta di un costruttore con parametri a una classe impedisce al compilatore di aggiungere il costruttore senza parametri. Questo spesso provoca modifiche accidentali di rilievo.

❌AVOID definire in modo esplicito i costruttori senza parametri sugli struct.

In questo modo la creazione di matrici più veloce, perché se il costruttore senza parametri non è definito, non deve essere eseguito in ogni slot della matrice. Si noti che molti compilatori, tra cui C , non consentono agli struct di avere costruttori senza parametri per questo motivo.

❌AVOID chiamando membri virtuali su un oggetto all'interno del relativo costruttore.

La chiamata a un membro virtuale causerà la chiamata dell'override più derivato, anche se il costruttore del tipo più derivato non è ancora stato eseguito completamente.

## <a name="type-constructor-guidelines"></a>Linee guida per i costruttori di tipoType Constructor Guidelines

✔️ rendere privati i costruttori statici.

Un costruttore statico, denominato anche costruttore di classe, viene utilizzato per inizializzare un tipo. CLR chiama il costruttore statico prima che venga creata la prima istanza del tipo o vengano chiamati tutti i membri statici su tale tipo. L'utente non ha alcun controllo su quando viene chiamato il costruttore statico. Se un costruttore statico non è privato, può essere chiamato da codice diverso da CLR. A seconda delle operazioni eseguite nel costruttore, ciò può causare un comportamento imprevisto. Il compilatore di C'è forza i costruttori statici per essere privati.

❌DO NOT generare eccezioni da costruttori statici.

Se viene generata un'eccezione da un costruttore di tipo, il tipo non è utilizzabile nel dominio applicazione corrente.

✔️ CONSIDER inizializzare i campi statici inline anziché utilizzare in modo esplicito i costruttori statici, perché il runtime è in grado di ottimizzare le prestazioni dei tipi che non dispongono di un costruttore statico definito in modo esplicito.

*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
