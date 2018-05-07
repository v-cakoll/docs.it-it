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
ms.openlocfilehash: 0d7ca279dc1626cd526910af93326280bcd8301d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="constructor-design"></a>Progettazione di costruttori
Esistono due tipi di costruttori: tipo di costruttori e dei costruttori di istanza.  
  
 Costruttori di tipo sono statici e vengono eseguiti da CLR prima che venga utilizzato il tipo. Costruttori di istanza eseguire quando viene creata un'istanza di un tipo.  
  
 Costruttori di tipo non possono accettare parametri. Costruttori di istanza possono. Costruttori di istanza che non accettano parametri vengono chiamati i costruttori predefiniti.  
  
 I costruttori sono il modo più semplice per creare istanze di un tipo. La maggior parte degli sviluppatori verranno cercare e tenta di utilizzare un costruttore prima ritengano modi alternativi per la creazione di istanze (ad esempio i metodi factory).  
  
 **✓ Provare a** fornendo semplice, in teoria predefiniti, costruttori.  
  
 Un costruttore semplice dispone di un numero molto ridotto di parametri e tutti i parametri sono primitive o enum. Tali costruttori semplici aumentano l'utilizzabilità di framework.  
  
 **✓ Provare a** utilizzando un metodo factory statico invece di un costruttore se la semantica dell'operazione desiderata non eseguano il mapping direttamente per la costruzione di una nuova istanza o seguendo le linee guida progettazione costruttore ritiene non naturale.  
  
 **✓ SI** utilizzare i parametri del costruttore come tasti di scelta rapida per l'impostazione delle proprietà principali.  
  
 Non deve esistere alcuna differenza nella semantica tra utilizzando il costruttore vuoto seguito da un set di proprietà e l'utilizzo di un costruttore con più argomenti.  
  
 **✓ SI** utilizzare lo stesso nome per i parametri del costruttore e una proprietà, se vengono utilizzati i parametri del costruttore è sufficiente impostare la proprietà.  
  
 L'unica differenza tra tali parametri e le proprietà debba essere maiuscole e minuscole.  
  
 **✓ SI** lavoro minimo nel costruttore.  
  
 I costruttori non memorizzare la quantità di lavoro diverso da acquisizione i parametri del costruttore. Il costo di qualsiasi altra elaborazione deve essere ritardato fino a quando non necessaria.  
  
 **✓ SI** generare eccezioni da costruttori di istanza, se appropriato.  
  
 **✓ SI** dichiarare in modo esplicito il costruttore predefinito pubblico nelle classi, se tale costruttore è obbligatorio.  
  
 Se si non dichiarano costruttori in modo esplicito su un tipo, molti linguaggi (ad esempio c#) aggiungerà automaticamente un costruttore predefinito pubblico. (Le classi astratte ottenere un costruttore protetto).  
  
 Aggiunta di un costruttore con parametri a una classe impedisce al compilatore di aggiungere il costruttore predefinito. In questo modo spesso modifiche accidentali.  
  
 **X evitare** definire in modo esplicito i costruttori predefiniti sulle strutture.  
  
 In questo modo la creazione della matrice più velocemente, in quanto se non è definito il costruttore predefinito, non deve essere eseguito su ogni slot nella matrice. Si noti che molti compilatori, inclusi c#, non consentano strutture possono contenere costruttori senza parametri per questo motivo.  
  
 **X evitare** chiamare membri virtuali su un oggetto all'interno di relativo costruttore.  
  
 La chiamata a un membro virtuale causerà la sostituzione più derivata da chiamare, anche se il costruttore del tipo più derivato non è stato completamente eseguito ancora.  
  
### <a name="type-constructor-guidelines"></a>Linee guida di costruttore di tipo  
 **✓ SI** rendere privato costruttori statici.  
  
 Un costruttore statico, denominato anche costruttore di classe, viene utilizzato per inizializzare un tipo. CLR chiama il costruttore statico prima viene creata la prima istanza del tipo o i membri statici su tale tipo sono chiamati. L'utente non dispone di alcun controllo sulla quando viene chiamato il costruttore statico. Se un costruttore statico non è privato, può essere chiamato da codice diverso da CLR. A seconda delle operazioni eseguite nel costruttore, questo può causare comportamenti imprevisti. Il compilatore c# forza costruttori statici come privato.  
  
 **X non** generare eccezioni da costruttori statici.  
  
 Se viene generata un'eccezione da un costruttore di tipo, il tipo non è utilizzabile nel dominio applicazione corrente.  
  
 **✓ Provare a** inizializzando i campi statici inline anziché in modo esplicito i costruttori statici, perché il runtime è in grado di ottimizzare le prestazioni dei tipi che non dispongono di un costruttore statico definito in modo esplicito.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
