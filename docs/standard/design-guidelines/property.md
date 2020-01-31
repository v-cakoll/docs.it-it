---
title: Progettazione di proprietà
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
ms.openlocfilehash: 8b6570b1b7c292729b78f2fe52f24f73319efe6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743660"
---
# <a name="property-design"></a>Progettazione di proprietà
Sebbene le proprietà siano tecnicamente molto simili ai metodi, sono piuttosto diverse in termini di scenari di utilizzo. Dovrebbero essere considerati campi intelligenti. Hanno la sintassi di chiamata dei campi e la flessibilità dei metodi.

 ✔️ creare proprietà solo Get se il chiamante non deve essere in grado di modificare il valore della proprietà.

 Tenere presente che se il tipo della proprietà è un tipo di riferimento modificabile, è possibile modificare il valore della proprietà anche se la proprietà è solo Get.

 ❌ non forniscono proprietà o proprietà solo set con il metodo set con accessibilità più ampia rispetto al Getter.

 Ad esempio, non usare le proprietà con un setter pubblico e un getter protetto.

 Se non è possibile specificare il getter della proprietà, implementare invece la funzionalità come metodo. Prendere in considerazione l'avvio del nome del metodo con `Set` e seguire il nome della proprietà. Ad esempio, <xref:System.AppDomain> dispone di un metodo denominato `SetCachePath` invece di avere una proprietà solo set denominata `CachePath`.

 ✔️ forniscono valori predefiniti ragionevoli per tutte le proprietà, assicurando che le impostazioni predefinite non comportino un problema di sicurezza o un codice inefficiente.

 ✔️ consentono di impostare le proprietà in qualsiasi ordine anche se ciò comporta uno stato temporaneo non valido dell'oggetto.

 È comune che due o più proprietà siano correlate a un punto in cui alcuni valori di una proprietà potrebbero non essere validi in base ai valori di altre proprietà nello stesso oggetto. In questi casi, le eccezioni derivanti dallo stato non valido devono essere posticipate fino a quando le proprietà correlate non vengono effettivamente utilizzate insieme dall'oggetto.

 ✔️ conservare il valore precedente se un metodo di impostazione della proprietà genera un'eccezione.

 ❌ evitare di generare eccezioni dai getter della proprietà.

 I getter della proprietà devono essere semplici operazioni e non devono avere precondizioni. Se un getter può generare un'eccezione, dovrebbe essere probabilmente riprogettato per essere un metodo. Si noti che questa regola non si applica agli indicizzatori, in cui si prevedono eccezioni come risultato della convalida degli argomenti.

### <a name="indexed-property-design"></a>Progettazione proprietà indicizzata
 Una proprietà indicizzata è una proprietà speciale che può avere parametri e può essere chiamata con una sintassi speciale simile all'indicizzazione della matrice.

 Le proprietà indicizzate sono comunemente definite indicizzatori. Gli indicizzatori devono essere usati solo nelle API che consentono di accedere agli elementi di una raccolta logica. Ad esempio, una stringa è una raccolta di caratteri e l'indicizzatore in <xref:System.String?displayProperty=nameWithType> è stato aggiunto per accedere ai relativi caratteri.

 ✔️ CONSIGLIABILE usare gli indicizzatori per fornire l'accesso ai dati archiviati in una matrice interna.

 ✔️ considerare la possibilità di fornire indicizzatori sui tipi che rappresentano raccolte di elementi.

 ❌ evitare di utilizzare proprietà indicizzate con più di un parametro.

 Se la progettazione richiede più parametri, riconsiderare se la proprietà rappresenta effettivamente una funzione di accesso a una raccolta logica. In caso contrario, utilizzare i metodi. Provare ad avviare il nome del metodo con `Get` o `Set`.

 ❌ evitare gli indicizzatori con tipi di parametro diversi da <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>o un'enumerazione.

 Se la progettazione richiede altri tipi di parametri, valutare fortemente se l'API rappresenta effettivamente una funzione di accesso a una raccolta logica. In caso contrario, usare un metodo. Provare ad avviare il nome del metodo con `Get` o `Set`.

 ✔️ utilizzare il nome `Item` per le proprietà indicizzate a meno che non esista un nome ovviamente migliore (ad esempio, vedere la proprietà <xref:System.String.Chars%2A> in `System.String`).

 In C#gli indicizzatori sono elementi denominati per impostazione predefinita. Il <xref:System.Runtime.CompilerServices.IndexerNameAttribute> può essere utilizzato per personalizzare questo nome.

 ❌ non forniscono un indicizzatore e metodi semanticamente equivalenti.

 ❌ non forniscono più di una famiglia di indicizzatori in overload in un unico tipo.

 Questa operazione viene applicata dal C# compilatore.

 ❌ non utilizzano proprietà indicizzate non predefinite.

 Questa operazione viene applicata dal C# compilatore.

### <a name="property-change-notification-events"></a>Eventi di notifica della modifica delle proprietà
 A volte è utile fornire un evento per notificare all'utente le modifiche apportate al valore di una proprietà. Ad esempio, `System.Windows.Forms.Control` genera un evento `TextChanged` dopo che il valore della relativa proprietà `Text` è stato modificato.

 ✔️ valutare la possibilità di generare eventi di notifica delle modifiche quando vengono modificati i valori delle proprietà nelle API di alto livello, in genere componenti di progettazione.

 Se è disponibile uno scenario valido che consente a un utente di conoscere quando una proprietà di un oggetto viene modificata, l'oggetto deve generare un evento di notifica delle modifiche per la proprietà.

 Tuttavia, è improbabile che valga l'overhead per generare eventi di questo tipo per le API di basso livello, ad esempio tipi di base o raccolte. Ad esempio, <xref:System.Collections.Generic.List%601> non genererebbe tali eventi quando un nuovo elemento viene aggiunto all'elenco e la proprietà `Count` viene modificata.

 ✔️ valutare la possibilità di generare eventi di notifica delle modifiche quando il valore di una proprietà viene modificato tramite forze esterne.

 Se il valore di una proprietà viene modificato tramite una forza esterna (in un modo diverso dalla chiamata ai metodi sull'oggetto), la generazione di eventi indica allo sviluppatore che il valore è in corso di modifica ed è stato modificato. Un esempio valido è la proprietà `Text` di un controllo casella di testo. Quando l'utente digita il testo in un `TextBox`, il valore della proprietà cambia automaticamente.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
