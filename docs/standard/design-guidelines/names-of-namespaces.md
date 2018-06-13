---
title: Nomi di spazi dei nomi
ms.date: 03/30/2017
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e0b6c5ac60474cfe984b3802e880eb58b017722
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576432"
---
# <a name="names-of-namespaces"></a>Nomi di spazi dei nomi
Come con altre linee guida di denominazione, l'obiettivo per la denominazione degli spazi dei nomi consiste nel creare chiarezza sufficiente per il programmatore utilizzando il framework di sapere immediatamente che cos'è probabilmente il contenuto dello spazio dei nomi. Il modello seguente specifica la regola generale per la denominazione degli spazi dei nomi:  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 Di seguito è riportati esempi:  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 **✓ SI** spazi dei nomi con un nome della società per evitare gli spazi dei nomi di società diverse da con lo stesso nome del prefisso.  
  
 **✓ SI** utilizzare un nome stabile e indipendente dalla versione del prodotto nel secondo livello di uno spazio dei nomi.  
  
 **X non** utilizzare gerarchie organizzative come base per i nomi nelle gerarchie dello spazio dei nomi, perché i nomi dei gruppi all'interno di aziende tendono a essere di breve durata. Organizzare la gerarchia di spazi dei nomi intorno a gruppi di tecnologie correlate.  
  
 **✓ SI** utilizzare il sistema Pascal e i componenti di spazio dei nomi separato con punti (ad esempio, `Microsoft.Office.PowerPoint`). Se il marchio viene utilizzata maiuscole e minuscole, è opportuno seguire le maiuscole e minuscole definite dal produttore, anche se esso devia dal maiuscole e minuscole normale spazio dei nomi.  
  
 **✓ Provare a** usando nomi plurali ove appropriato.  
  
 Ad esempio, utilizzare `System.Collections` anziché `System.Collection`. Marchi e gli acronimi sono tuttavia eccezioni a questa regola. Ad esempio, utilizzare `System.IO` anziché `System.IOs`.  
  
 **X non** utilizzare lo stesso nome per uno spazio dei nomi e un tipo nello spazio dei nomi.  
  
 Ad esempio, non utilizzare `Debug` come uno spazio dei nomi nome e quindi fornire anche una classe denominata `Debug` dello stesso spazio dei nomi. Alcuni compilatori richiedono tali tipi completi.  
  
### <a name="namespaces-and-type-name-conflicts"></a>Spazi dei nomi e i conflitti di nome di tipo  
 **X non** introducono i nomi di tipo generico, ad esempio `Element`, `Node`, `Log`, e `Message`.  
  
 È molto probabile che verranno provocare per digitare nome è in conflitto in comune scenari. È necessario qualificare i nomi di tipo generico (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).  
  
 Sono disponibili linee guida specifiche per evitare conflitti di nomi per le diverse categorie di spazi dei nomi.  
  
-   **Spazi dei nomi del modello di applicazione**  
  
     Spazi dei nomi appartenenti a un modello di applicazione single molto spesso vengono utilizzati insieme, ma vengono non utilizzati quasi mai con spazi dei nomi di altri modelli di applicazione. Ad esempio, il <xref:System.Windows.Forms?displayProperty=nameWithType> dello spazio dei nomi è raramente utilizzata in combinazione con il <xref:System.Web.UI?displayProperty=nameWithType> dello spazio dei nomi. Di seguito è riportato un elenco noto modello dello spazio dei nomi di gruppi di applicazioni:  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X non** assegnare lo stesso nome per i tipi negli spazi dei nomi all'interno di un modello di applicazione singolo.  
  
     Ad esempio, non aggiungere un tipo denominato `Page` per il <xref:System.Web.UI.Adapters?displayProperty=nameWithType> dello spazio dei nomi, perché il <xref:System.Web.UI?displayProperty=nameWithType> spazio dei nomi contiene già un tipo denominato `Page`.  
  
-   **Spazi dei nomi dell'infrastruttura**  
  
     Questo gruppo contiene spazi dei nomi che raramente vengono importati durante lo sviluppo di applicazioni comuni. Ad esempio, `.Design` gli spazi dei nomi sono utilizzati principalmente durante lo sviluppo di programmazione degli strumenti. Come evitare conflitti con i tipi in questi spazi dei nomi non è critico.  
  
-   **Spazi dei nomi dei componenti di base**  
  
     Spazi dei nomi principali includono tutti `System` spazi dei nomi, esclusi gli spazi dei nomi dei modelli di applicazione e gli spazi dei nomi dell'infrastruttura. Spazi dei nomi principali includono, ad esempio, `System`, `System.IO`, `System.Xml`, e `System.Net`.  
  
     **X non** consentono di tipi di nomi in conflitto con qualsiasi tipo negli spazi dei nomi dei componenti di base.  
  
     Ad esempio, non utilizzare mai `Stream` come nome di tipo. Genererebbe un conflitto con <xref:System.IO.Stream?displayProperty=nameWithType>, molto usati tipo.  
  
-   **Gruppi di spazio dei nomi di tecnologia**  
  
     Questa categoria include tutti gli spazi dei nomi con i primi due nodi dello spazio dei nomi stesso `(<Company>.<Technology>*`), ad esempio `Microsoft.Build.Utilities` e `Microsoft.Build.Tasks`. È importante che i tipi appartenenti a una singola tecnologia non siano in conflitto tra loro.  
  
     **X non** assegnare nomi dei tipi che possano entrare in conflitto con altri tipi all'interno di una singola tecnologia.  
  
     **X non** introdurre conflitti di nomi tra i tipi negli spazi dei nomi di tecnologia e uno spazio dei nomi del modello di applicazione (a meno che la tecnologia non deve essere utilizzato con il modello di applicazione).  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
