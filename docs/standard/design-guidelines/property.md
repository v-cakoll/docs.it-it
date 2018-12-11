---
title: Progettazione di proprietà
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
author: KrzysztofCwalina
ms.openlocfilehash: 1d119b48f0524b3e997aa2cb9ea2cbbd855afdf0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131456"
---
# <a name="property-design"></a>Progettazione di proprietà
Anche se le proprietà sono tecnicamente è molto simile ai metodi, essi sono piuttosto diversi in termini relativi scenari di utilizzo. Si dovrebbero essere considerate come campi intelligenti. Con la sintassi per la chiamata di campi e la flessibilità dei metodi.  
  
 **✓ DO** creare proprietà get-only, se il chiamante non deve essere in grado di modificare il valore della proprietà.  
  
 Tenere presente che se il tipo di proprietà è un tipo di riferimento modificabile, il valore della proprietà può essere modificato anche se la proprietà è di sola ricezione.  
  
 **X DO NOT** fornire solo set di proprietà o il setter con accessibilità più ampia rispetto al metodo Get.  
  
 Ad esempio, non utilizzare le proprietà con un setter pubblico e un metodo di richiamo protetto.  
  
 Se non è possibile fornire il getter della proprietà, invece implementare la funzionalità di un metodo. È consigliabile iniziare con il nome del metodo `Set` e completa con ciò che si avrebbero denominato della proprietà. Ad esempio, <xref:System.AppDomain> ha un metodo denominato `SetCachePath` invece di avere una set di proprietà di sola `CachePath`.  
  
 **✓ DO** fornire valori predefiniti appropriati per tutte le proprietà, assicurandosi che le impostazioni predefinite non comportano un problema di sicurezza o di codice particolarmente inefficiente.  
  
 **✓ DO** consentono di proprietà da impostare in qualsiasi ordine, anche se ciò comporta un stato temporaneo non valido dell'oggetto.  
  
 È comune per due o più proprietà correlate a un punto in cui alcuni valori di una proprietà potrebbero essere non validi in base ai valori delle altre proprietà nello stesso oggetto. In questi casi, le eccezioni derivanti dallo stato non valido devono essere posticipate fino a quando non le proprietà correlate vengono effettivamente usate insieme dall'oggetto.  
  
 **✓ DO** mantenere il valore precedente se un setter di proprietà genera un'eccezione.  
  
 **X AVOID** generazione di eccezioni da metodi get di proprietà.  
  
 Getter proprietà devono essere operazioni semplici e non deve contenere tutte le precondizioni. Se un metodo Get può generare un'eccezione, probabile che deve essere riprogettato per essere un metodo. Si noti che questa regola non valida per gli indicizzatori, in cui si prevede che le eccezioni come risultato di convalida di argomenti.  
  
### <a name="indexed-property-design"></a>Progettazione di proprietà indicizzate  
 Una proprietà indicizzata è una proprietà speciale che può avere parametri e può essere chiamata con una sintassi speciale simile per l'indicizzazione della matrice.  
  
 Proprietà indicizzate sono comunemente detto indicizzatori. Gli indicizzatori devono essere utilizzati solo nelle API che consentono l'accesso agli elementi in una raccolta logica. Ad esempio, una stringa è una raccolta di caratteri e l'indicizzatore su <xref:System.String?displayProperty=nameWithType> è stato aggiunto per accedere ai relativi caratteri.  
  
 **✓ CONSIDER** utilizzo degli indicizzatori per fornire l'accesso ai dati archiviati in una matrice interna.  
  
 **✓ CONSIDER** fornendo gli indicizzatori in tipi che rappresentano raccolte di elementi.  
  
 **X AVOID** utilizzando proprietà con più di un parametro indicizzate.  
  
 Se il progetto richiede più parametri, verificare che la proprietà rappresenta effettivamente una funzione di accesso a una raccolta logica. In caso contrario, usare invece i metodi. È consigliabile iniziare con il nome del metodo `Get` o `Set`.  
  
 **X AVOID** indicizzatori con tipi di parametro diverso da <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, o un'enumerazione.  
  
 Se il progetto richiede altri tipi di parametri, rivalutare se l'API rappresenta effettivamente una funzione di accesso a una raccolta logica. In caso contrario, usare un metodo. È consigliabile iniziare con il nome del metodo `Get` o `Set`.  
  
 **✓ DO** usare il nome `Item` per proprietà indicizzate, a meno che non è un nome migliore ovviamente (ad esempio, vedere il <xref:System.String.Chars%2A> proprietà `System.String`).  
  
 In c#, gli indicizzatori sono per impostazione predefinita denominata elemento. Il <xref:System.Runtime.CompilerServices.IndexerNameAttribute> può essere utilizzato per personalizzare il nome specificato.  
  
 **X DO NOT** fornire sia un indicizzatore e metodi che sono semanticamente equivalenti.  
  
 **X DO NOT** specificare più di un gruppo di overload indicizzatori in un solo tipo.  
  
 Questo viene applicato dal compilatore c#.  
  
 **X DO NOT** diversi da quelli predefiniti utilizzare proprietà indicizzate.  
  
 Questo viene applicato dal compilatore c#.  
  
### <a name="property-change-notification-events"></a>Eventi di notifica di modifica proprietà  
 In alcuni casi è utile fornire un evento notificando all'utente di modifiche in un valore della proprietà. Ad esempio, `System.Windows.Forms.Control` genera una `TextChanged` eventi quando il valore della relativa `Text` proprietà è stata modificata.  
  
 **✓ CONSIDER** generato modificare eventi di notifica quando vengono modificati i valori delle proprietà generale per le API (in genere Progettazione componenti).  
  
 Se si verifica uno scenario importante per un utente di sapere quando una proprietà di un oggetto in fase di modifica, l'oggetto deve generare un evento di notifica di modifica per la proprietà.  
  
 Tuttavia, è probabilmente non vale la pena l'overhead per generare tali eventi per le API di basso livello, ad esempio i tipi di base o raccolte. Ad esempio, <xref:System.Collections.Generic.List%601> non genera eventi di questo tipo quando viene aggiunto un nuovo elemento all'elenco e `Count` le modifiche alle proprietà.  
  
 **✓ CONSIDER** generato modificare eventi di notifica quando il valore di una proprietà viene modificato tramite forze esterne.  
  
 Se un valore della proprietà viene modificato tramite alcuni force esterno (in modo diverso da chiamando i metodi sull'oggetto), generare eventi indicano agli sviluppatori che il valore in fase di modifica e che è stato modificato. Un buon esempio è il `Text` proprietà di un controllo casella di testo. Quando l'utente digita del testo in un `TextBox`, modifica automaticamente il valore della proprietà.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
