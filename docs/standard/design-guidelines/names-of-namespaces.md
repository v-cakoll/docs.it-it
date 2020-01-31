---
title: Nomi di spazi dei nomi
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 52fee0dfaff284c2c1a6afcb8aa7530c28a60d65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744148"
---
# <a name="names-of-namespaces"></a>Nomi di spazi dei nomi
Come per le altre linee guida per la denominazione, l'obiettivo di denominare gli spazi dei nomi consiste nel creare una chiarezza sufficiente per il programmatore che usa il Framework per conoscere immediatamente il contenuto dello spazio dei nomi. Nel modello seguente viene specificata la regola generale per la denominazione degli spazi dei nomi:

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 Di seguito sono riportati alcuni esempi:

 `Fabrikam.Math` `Litware.Security`

 ✔️ i nomi degli spazi dei nomi prefissi con il nome della società per impedire che gli spazi dei nomi di società diverse abbiano lo stesso nome.

 ✔️ utilizzare un nome di prodotto stabile e indipendente dalla versione al secondo livello del nome di uno spazio dei nomi.

 ❌ non utilizzano gerarchie organizzative come base per i nomi nelle gerarchie dello spazio dei nomi, perché i nomi dei gruppi all'interno delle aziende tendono a essere di breve durata. Organizzare la gerarchia di spazi dei nomi intorno ai gruppi di tecnologie correlate.

 ✔️ utilizzare sistema Pascal e separare i componenti dello spazio dei nomi con punti, ad esempio `Microsoft.Office.PowerPoint`. Se il marchio usa una combinazione di maiuscole e minuscole non tradizionale, è necessario seguire la combinazione di maiuscole e minuscole definita dal marchio, anche se si devia dalla normale combinazione dello spazio dei nomi

 ✔️ CONSIGLIABILE utilizzare nomi di spazi dei nomi plurali laddove appropriato.

 Ad esempio, usare `System.Collections` invece di `System.Collection`. I nomi e gli acronimi delle marche sono tuttavia eccezioni a questa regola. Ad esempio, usare `System.IO` invece di `System.IOs`.

 ❌ non utilizzano lo stesso nome per uno spazio dei nomi e un tipo in tale spazio dei nomi.

 Ad esempio, non usare `Debug` come nome dello spazio dei nomi e quindi fornire anche una classe denominata `Debug` nello stesso spazio dei nomi. Molti compilatori richiedono che tali tipi siano completi.

### <a name="namespaces-and-type-name-conflicts"></a>Conflitti di spazi dei nomi e nomi di tipo
 ❌ non introducono nomi di tipo generico, ad esempio `Element`, `Node`, `Log`e `Message`.

 È molto probabile che questa operazione provochi conflitti tra i nomi dei tipi negli scenari comuni. È necessario qualificare i nomi di tipo generico (`FormElement`, `XmlNode`, `EventLog``SoapMessage`).

 Esistono linee guida specifiche per evitare conflitti tra nomi di tipi per diverse categorie di spazi dei nomi.

- **Spazi dei nomi del modello di applicazione**

     Gli spazi dei nomi che appartengono a un singolo modello di applicazione vengono spesso usati insieme, ma non vengono usati quasi mai con gli spazi dei nomi di altri modelli di applicazione. Ad esempio, lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> viene usato molto raramente insieme allo spazio dei nomi <xref:System.Web.UI?displayProperty=nameWithType>. Di seguito è riportato un elenco di gruppi di spazi dei nomi del modello di applicazione ben noti:

     `System.Windows*` `System.Web.UI*`

     ❌ non assegnano lo stesso nome ai tipi negli spazi dei nomi all'interno di un singolo modello di applicazione.

     Non aggiungere ad esempio un tipo denominato `Page` allo spazio dei nomi <xref:System.Web.UI.Adapters?displayProperty=nameWithType>, perché lo spazio dei nomi <xref:System.Web.UI?displayProperty=nameWithType> già contiene un tipo denominato `Page`.

- **Spazi dei nomi dell'infrastruttura**

     Questo gruppo contiene spazi dei nomi importati raramente durante lo sviluppo di applicazioni comuni. Ad esempio, `.Design` gli spazi dei nomi vengono utilizzati principalmente per lo sviluppo di strumenti di programmazione. Evitare conflitti con i tipi in questi spazi dei nomi non è fondamentale.

- **Spazi dei nomi principali**

     Gli spazi dei nomi principali includono tutti gli spazi dei nomi `System`, esclusi gli spazi dei nomi dei modelli di applicazione e gli spazi dei nomi dell'infrastruttura. Gli spazi dei nomi principali includono, tra gli altri, `System`, `System.IO`, `System.Xml`e `System.Net`.

     ❌ non assegnano nomi di tipi che potrebbero entrare in conflitto con qualsiasi tipo negli spazi dei nomi di base.

     Ad esempio, non usare mai `Stream` come nome di tipo. Si verificherebbe un conflitto con <xref:System.IO.Stream?displayProperty=nameWithType>, un tipo di uso molto comune.

- **Gruppi di spazi dei nomi tecnologici**

     Questa categoria include tutti gli spazi dei nomi con gli stessi primi due nodi dello spazio dei nomi `(<Company>.<Technology>*`), ad esempio `Microsoft.Build.Utilities` e `Microsoft.Build.Tasks`. È importante che i tipi che appartengono a una singola tecnologia non siano in conflitto tra loro.

     ❌ non assegnano nomi di tipi che potrebbero essere in conflitto con altri tipi all'interno di una singola tecnologia.

     ❌ non introducono conflitti tra i tipi negli spazi dei nomi della tecnologia e uno spazio dei nomi del modello applicativo, a meno che la tecnologia non sia destinata all'utilizzo con il modello di applicazione.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
