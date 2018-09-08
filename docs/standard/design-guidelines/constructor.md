---
title: Progettazione di costruttori
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ad920c8028b102a13fdfe928d21768538e25b0f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44180449"
---
# <a name="constructor-design"></a>Progettazione di costruttori
Esistono due tipi di costruttori: digitare costruttori e i costruttori di istanza.  
  
 I costruttori di tipi sono statici e vengono eseguiti da CLR prima che venga utilizzato il tipo. Costruttori di istanza eseguire quando viene creata un'istanza di un tipo.  
  
 I costruttori di tipi non accettano alcun parametro. Costruttori di istanza possono. Costruttori di istanze che non accettano alcun parametro spesso vengono chiamati i costruttori predefiniti.  
  
 I costruttori sono il modo più semplice per creare istanze di un tipo. La maggior parte degli sviluppatori saranno ricerca e provare a usare un costruttore prima che essi prendere in considerazione modi alternativi per la creazione di istanze (ad esempio, metodi factory).  
  
 **✓ CONSIDER** fornendo semplice, in teoria predefiniti, costruttori.  
  
 Un costruttore semplice ha un numero molto ridotto di parametri e tutti i parametri sono primitive o enum. Questi costruttori semplici aumentano l'utilizzabilità del framework.  
  
 **✓ CONSIDER** utilizzando un metodo factory statico invece di un costruttore se la semantica dell'operazione desiderata non eseguano il mapping direttamente per la costruzione di una nuova istanza o seguendo le linee guida progettazione costruttore ritiene non naturale.  
  
 **✓ DO** utilizzare i parametri del costruttore come tasti di scelta rapida per l'impostazione delle proprietà principali.  
  
 Non vi sarà alcuna differenza semantica tra usando il costruttore vuoto seguito da alcuni set di proprietà e usando un costruttore con più argomenti.  
  
 **✓ DO** utilizzare lo stesso nome per i parametri del costruttore e una proprietà, se vengono utilizzati i parametri del costruttore è sufficiente impostare la proprietà.  
  
 L'unica differenza tra tali parametri e le proprietà debba essere maiuscole e minuscole.  
  
 **✓ DO** lavoro minimo nel costruttore.  
  
 I costruttori non occorre eseguire la quantità di lavoro diverso da acquisizione i parametri del costruttore. Il costo di qualsiasi altra elaborazione dovrebbe risultare ritardato fino al necessario.  
  
 **✓ DO** generare eccezioni da costruttori di istanza, se appropriato.  
  
 **✓ DO** dichiarare in modo esplicito il costruttore predefinito pubblico nelle classi, se tale costruttore è obbligatorio.  
  
 Se si non dichiarano alcun costruttore in modo esplicito su un tipo, molti linguaggi (ad esempio, c#) aggiungerà automaticamente un costruttore predefinito pubblico. (Le classi astratte ottenere un costruttore protetto).  
  
 Aggiunta di un costruttore con parametri a una classe impedisce al compilatore di aggiungere il costruttore predefinito. Ciò spesso causa modifiche di rilievo accidentale.  
  
 **X AVOID** definire in modo esplicito i costruttori predefiniti sulle strutture.  
  
 In questo modo la creazione della matrice meno tempo, in quanto se non è definito il costruttore predefinito, non deve essere eseguito su ogni slot nella matrice. Si noti che molti compilatori, tra cui c#, non consentano strutture possono avere costruttori senza parametri per questo motivo.  
  
 **X AVOID** chiamare membri virtuali su un oggetto all'interno di relativo costruttore.  
  
 La chiamata a un membro virtuale provocherà la sostituzione più derivata da chiamare, anche se il costruttore del tipo più derivato non è stato completamente eseguito ancora.  
  
### <a name="type-constructor-guidelines"></a>Linee guida di costruttore di tipo  
 **✓ DO** rendere privato costruttori statici.  
  
 Un costruttore statico, denominato anche costruttore di classe, viene utilizzato per inizializzare un tipo. CLR chiama il costruttore statico prima che venga creata la prima istanza del tipo o qualsiasi membro statico sul quel tipo viene chiamati. L'utente non ha alcun controllo su quando viene chiamato il costruttore statico. Se un costruttore statico non è privato, può essere chiamata dal codice diverso da CLR. A seconda delle operazioni eseguite nel costruttore, ciò può provocare comportamenti imprevisti. Il compilatore C# forza i costruttori statici come privato.  
  
 **X DO NOT** generare eccezioni da costruttori statici.  
  
 Se viene generata un'eccezione da un costruttore di tipo, il tipo non è utilizzabile nel dominio dell'applicazione corrente.  
  
 **✓ CONSIDER** inizializzando i campi statici inline anziché in modo esplicito i costruttori statici, perché il runtime è in grado di ottimizzare le prestazioni dei tipi che non dispongono di un costruttore statico definito in modo esplicito.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
