---
title: "Progettazione di proprietà"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 477b3b69ce1b8a3bb160e8e120885239e3d99e56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="property-design"></a>Progettazione di proprietà
Anche se tecnicamente molto simile ai metodi, proprietà sono diversi in termini relativi scenari di utilizzo. Si dovrebbero essere considerate come campi intelligenti. Hanno la sintassi per la chiamata di campi e la flessibilità dei metodi.  
  
 **✓ SI** creare le proprietà di sola lettura se il chiamante non deve essere in grado di modificare il valore della proprietà.  
  
 Tenere presente che se il tipo di proprietà è un tipo di riferimento modificabile, il valore della proprietà può essere modificato anche se la proprietà solo get.  
  
 **X non** fornire solo set di proprietà o il setter con accessibilità più ampia rispetto al metodo Get.  
  
 Ad esempio, non utilizzare proprietà con un setter pubblico e un metodo di richiamo protetto.  
  
 Se il metodo Get della proprietà non può essere fornito, è possibile implementare la funzionalità di un metodo. È consigliabile iniziare con il nome del metodo `Set` e seguire con ciò che si avrebbero denominato la proprietà. Ad esempio, <xref:System.AppDomain> ha un metodo denominato `SetCachePath` anziché una set di proprietà di sola `CachePath`.  
  
 **✓ SI** fornire valori predefiniti appropriati per tutte le proprietà, assicurandosi che le impostazioni predefinite non comportano un problema di sicurezza o di codice particolarmente inefficiente.  
  
 **✓ SI** consente di proprietà da impostare in qualsiasi ordine, anche se il risultato è un stato temporaneo non valido dell'oggetto.  
  
 È comune per due o più delle proprietà correlate a un punto in cui alcuni valori di una proprietà potrebbero essere non validi in base ai valori di altre proprietà sull'oggetto stesso. In questi casi, le eccezioni derivanti da stato non valido devono essere rinviate fino a quando le proprietà correlate vengono effettivamente utilizzate insieme dall'oggetto.  
  
 **✓ SI** mantenere il valore precedente, se un setter di proprietà genera un'eccezione.  
  
 **X evitare** la generazione di eccezioni da metodi get di proprietà.  
  
 Metodi get di proprietà devono essere operazioni semplici e non deve avere le precondizioni. Se un metodo Get può generare un'eccezione, deve probabilmente riprogettato per essere un metodo. Si noti che questa regola viene applicata per gli indicizzatori, in cui è prevista eccezioni come risultato di convalida gli argomenti.  
  
### <a name="indexed-property-design"></a>Progettazione di proprietà indicizzate  
 Una proprietà indicizzata è una proprietà speciale che può avere parametri e può essere chiamata con una sintassi speciale simile all'indicizzazione di matrice.  
  
 Proprietà indicizzate sono conosciute come gli indicizzatori. Gli indicizzatori devono essere utilizzati solo nelle API che forniscono l'accesso agli elementi in una raccolta logica. Ad esempio, una stringa è un insieme di caratteri e l'indicizzatore in <xref:System.String?displayProperty=nameWithType> è stato aggiunto per accedere ai relativi caratteri.  
  
 **Provare a ✓** utilizzo degli indicizzatori per fornire l'accesso ai dati archiviati in una matrice interna.  
  
 **Provare a ✓** fornendo gli indicizzatori in tipi che rappresentano raccolte di elementi.  
  
 **X evitare** utilizzando proprietà con più di un parametro indicizzate.  
  
 Se la progettazione richiede più parametri, verificare che la proprietà rappresenta una funzione di accesso a un insieme logico. In caso contrario, è possibile utilizzare metodi. È consigliabile iniziare con il nome del metodo `Get` o `Set`.  
  
 **X evitare** indicizzatori con tipi di parametro diverso da <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, o un'enumerazione.  
  
 Se il progetto richiede altri tipi di parametri, rivalutare se l'API rappresenta una funzione di accesso a un insieme logico. In caso contrario, utilizzare un metodo. È consigliabile iniziare con il nome del metodo `Get` o `Set`.  
  
 **✓ SI** utilizzare il nome `Item` per le proprietà indicizzate, a meno che non è un nome chiaramente più (ad esempio, vedere il <xref:System.String.Chars%2A> proprietà `System.String`).  
  
 In c#, gli indicizzatori sono per impostazione predefinita l'elemento denominato. Il <xref:System.Runtime.CompilerServices.IndexerNameAttribute> può essere utilizzato per personalizzare questo nome.  
  
 **X non** fornire sia un indicizzatore e i metodi sono semanticamente equivalenti.  
  
 **X non** fornire più di una famiglia di indicizzatori overload in un solo tipo.  
  
 Questo viene applicato dal compilatore c#.  
  
 **X non** non predefinite utilizzare proprietà indicizzate.  
  
 Questo viene applicato dal compilatore c#.  
  
### <a name="property-change-notification-events"></a>Eventi di notifica di modifica di proprietà  
 Talvolta è utile fornire un evento di notificare all'utente di modifiche in un valore della proprietà. Ad esempio, `System.Windows.Forms.Control` genera un `TextChanged` eventi quando il valore della relativa `Text` proprietà è stata modificata.  
  
 **Provare a ✓** generato modificare eventi di notifica quando vengono modificati i valori delle proprietà generale per le API (in genere della finestra di progettazione componenti).  
  
 Se è presente uno scenario ottimo per un utente di conoscere quando si modifica una proprietà di un oggetto, l'oggetto deve generare un evento di notifica di modifica per la proprietà.  
  
 Tuttavia, non viene in genere valere la pena l'overhead per generare tali eventi per le API di basso livello, ad esempio tipi di base o raccolte. Ad esempio, <xref:System.Collections.Generic.List%601> potrebbe non generare tali eventi quando un nuovo elemento viene aggiunto all'elenco e `Count` le modifiche alle proprietà.  
  
 **Provare a ✓** generato modificare eventi di notifica quando cambia il valore di una proprietà tramite forze esterne.  
  
 Se un valore della proprietà viene modificata tramite alcuni forza esterna (in modo diverso da chiamando i metodi per l'oggetto), generare gli eventi indicano allo sviluppatore che il valore in fase di modifica e che è stato modificato. Un buon esempio è la `Text` proprietà di un controllo casella di testo. Quando l'utente digita il testo in un `TextBox`, viene automaticamente modificato il valore della proprietà.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione di membro](../../../docs/standard/design-guidelines/member.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
