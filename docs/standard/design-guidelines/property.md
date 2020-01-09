---
title: Progettazione di proprietà
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
ms.openlocfilehash: 5d5cdbfdb38c7aebaca6cbcdeb63959ac12884e0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709127"
---
# <a name="property-design"></a>Progettazione di proprietà
Sebbene le proprietà siano tecnicamente molto simili ai metodi, sono piuttosto diverse in termini di scenari di utilizzo. Dovrebbero essere considerati campi intelligenti. Hanno la sintassi di chiamata dei campi e la flessibilità dei metodi.  
  
 **✓ DO** creare proprietà get-only, se il chiamante non deve essere in grado di modificare il valore della proprietà.  
  
 Tenere presente che se il tipo della proprietà è un tipo di riferimento modificabile, è possibile modificare il valore della proprietà anche se la proprietà è solo Get.  
  
 **X DO NOT** fornire solo set di proprietà o il setter con accessibilità più ampia rispetto al metodo Get.  
  
 Ad esempio, non usare le proprietà con un setter pubblico e un getter protetto.  
  
 Se non è possibile specificare il getter della proprietà, implementare invece la funzionalità come metodo. Prendere in considerazione l'avvio del nome del metodo con `Set` e seguire il nome della proprietà. Ad esempio, <xref:System.AppDomain> dispone di un metodo denominato `SetCachePath` invece di avere una proprietà solo set denominata `CachePath`.  
  
 **✓ DO** fornire valori predefiniti appropriati per tutte le proprietà, assicurandosi che le impostazioni predefinite non comportano un problema di sicurezza o di codice particolarmente inefficiente.  
  
 **✓ DO** consentono di proprietà da impostare in qualsiasi ordine, anche se ciò comporta un stato temporaneo non valido dell'oggetto.  
  
 È comune che due o più proprietà siano correlate a un punto in cui alcuni valori di una proprietà potrebbero non essere validi in base ai valori di altre proprietà nello stesso oggetto. In questi casi, le eccezioni derivanti dallo stato non valido devono essere posticipate fino a quando le proprietà correlate non vengono effettivamente utilizzate insieme dall'oggetto.  
  
 **✓ DO** mantenere il valore precedente se un setter di proprietà genera un'eccezione.  
  
 **X AVOID** generazione di eccezioni da metodi get di proprietà.  
  
 I getter della proprietà devono essere semplici operazioni e non devono avere precondizioni. Se un getter può generare un'eccezione, dovrebbe essere probabilmente riprogettato per essere un metodo. Si noti che questa regola non si applica agli indicizzatori, in cui si prevedono eccezioni come risultato della convalida degli argomenti.  
  
### <a name="indexed-property-design"></a>Progettazione proprietà indicizzata  
 Una proprietà indicizzata è una proprietà speciale che può avere parametri e può essere chiamata con una sintassi speciale simile all'indicizzazione della matrice.  
  
 Le proprietà indicizzate sono comunemente definite indicizzatori. Gli indicizzatori devono essere usati solo nelle API che consentono di accedere agli elementi di una raccolta logica. Ad esempio, una stringa è una raccolta di caratteri e l'indicizzatore in <xref:System.String?displayProperty=nameWithType> è stato aggiunto per accedere ai relativi caratteri.  
  
 **✓ CONSIDER** utilizzo degli indicizzatori per fornire l'accesso ai dati archiviati in una matrice interna.  
  
 **✓ CONSIDER** fornendo gli indicizzatori in tipi che rappresentano raccolte di elementi.  
  
 **X AVOID** utilizzando proprietà con più di un parametro indicizzate.  
  
 Se la progettazione richiede più parametri, riconsiderare se la proprietà rappresenta effettivamente una funzione di accesso a una raccolta logica. In caso contrario, utilizzare i metodi. Provare ad avviare il nome del metodo con `Get` o `Set`.  
  
 **X AVOID** indicizzatori con tipi di parametro diverso da <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, o un'enumerazione.  
  
 Se la progettazione richiede altri tipi di parametri, valutare fortemente se l'API rappresenta effettivamente una funzione di accesso a una raccolta logica. In caso contrario, usare un metodo. Provare ad avviare il nome del metodo con `Get` o `Set`.  
  
 **✓ DO** usare il nome `Item` per proprietà indicizzate, a meno che non è un nome migliore ovviamente (ad esempio, vedere il <xref:System.String.Chars%2A> proprietà `System.String`).  
  
 In C#gli indicizzatori sono elementi denominati per impostazione predefinita. Il <xref:System.Runtime.CompilerServices.IndexerNameAttribute> può essere utilizzato per personalizzare questo nome.  
  
 **X DO NOT** fornire sia un indicizzatore e metodi che sono semanticamente equivalenti.  
  
 **X DO NOT** specificare più di un gruppo di overload indicizzatori in un solo tipo.  
  
 Questa operazione viene applicata dal C# compilatore.  
  
 **X DO NOT** diversi da quelli predefiniti utilizzare proprietà indicizzate.  
  
 Questa operazione viene applicata dal C# compilatore.  
  
### <a name="property-change-notification-events"></a>Eventi di notifica della modifica delle proprietà  
 A volte è utile fornire un evento per notificare all'utente le modifiche apportate al valore di una proprietà. Ad esempio, `System.Windows.Forms.Control` genera un evento `TextChanged` dopo che il valore della relativa proprietà `Text` è stato modificato.  
  
 **✓ CONSIDER** generato modificare eventi di notifica quando vengono modificati i valori delle proprietà generale per le API (in genere Progettazione componenti).  
  
 Se è disponibile uno scenario valido che consente a un utente di conoscere quando una proprietà di un oggetto viene modificata, l'oggetto deve generare un evento di notifica delle modifiche per la proprietà.  
  
 Tuttavia, è improbabile che valga l'overhead per generare eventi di questo tipo per le API di basso livello, ad esempio tipi di base o raccolte. Ad esempio, <xref:System.Collections.Generic.List%601> non genererebbe tali eventi quando un nuovo elemento viene aggiunto all'elenco e la proprietà `Count` viene modificata.  
  
 **✓ CONSIDER** generato modificare eventi di notifica quando il valore di una proprietà viene modificato tramite forze esterne.  
  
 Se il valore di una proprietà viene modificato tramite una forza esterna (in un modo diverso dalla chiamata ai metodi sull'oggetto), la generazione di eventi indica allo sviluppatore che il valore è in corso di modifica ed è stato modificato. Un esempio valido è la proprietà `Text` di un controllo casella di testo. Quando l'utente digita il testo in un `TextBox`, il valore della proprietà cambia automaticamente.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
